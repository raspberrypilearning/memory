## 높은 점수

이제 높은 점수를 저장하여 친구들과 놀 수 있습니다.

\--- task \---

`높은 점수`{:class="block3variables"}와 `이름`{:class="block3variables"}이라는 두 개의 새 변수를 만듭니다.

\--- /task \---

플레이어가 순서를 틀리게하여 게임이 종료되면 게임은 점수가 현재 최고 점수보다 높은지 확인해야 합니다. 그렇다면 게임은 점수를 최고 점수로 저장하고 플레이어의 이름도 저장해야 합니다.

\--- task \---

`높은 점수`{:class="block3variables"}를 저장하는 코드를 캐릭터 스프라이트에 추가합니다. 이름이 `이름`{:class="block3variables"} 변수에 저장되어 있어야 합니다.

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

새 코드는 다음 패턴을 따라야 합니다.

`게임 오버`{:class="block3looks"} 메시지 다음에 `만약`{:class="block3control"} the `스코어`{:class="block3variables"} 가 `>`{:class="block3operators"} the `하이스코어`{:class="block3variables"} 이면, `정하기`{:class="block3variables"} 블록을 사용하여 `하이스코어`{:class="block3variables"} 를 `스코어`{:class="block3variables"}로 설정합니다. 플레이어의 이름을 `묻고 기다리기`{:class="block3sensing"} 하여 `정하기`{:class="block3variables"} 블록을 사용하여 `이름`{:class="block3variables"} 을 `대답`{:class="block3sensing"}으로 합니다.

\--- /hint \---

\--- hint \---

다음 블록이 필요합니다.

![발레리나](images/ballerina.png)

```blocks3
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(high score)

ask [What's your name?] and wait

set [high score v] to [ ] 

set [name v] to [ ] 
```

\--- /hint \---

\--- hint \---

빨간색 버튼을 눌렀을 때의 코드는 다음과 같습니다.

![발레리나](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (item (1 v) of [sequence v]) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    if < (score :: variables) > (high score) > then
        set [high score v] to (score :: variables)
        ask [High score! What is your name?] and wait
        set [name v] to (answer)
    end
    stop [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

다른 세 가지 색상의 캐릭터 스프라이트 에도 이 새 코드를 추가해야합니다!

네 가지 색상 각각의 '게임 오버' 코드가 정확히 동일하다는 것을 알 수 있습니까?

![발레리나](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

예를 들어 사운드를 추가하거나 '게임 오버' 메시지를 변경하기 위해, 코드를 변경해야 하는 경우 총 4 번 변경해야합니다. 이는 많은 시간을 낭비합니다.

대신 고유한 코드 블록을 정의하고 프로젝트의 어느 곳에서나 사용할 수 있습니다.

\--- task \---

`나만의 블록`{:class="block3myblocks"}을 클릭하여, **블록 만들기** 합니다. 블록의 이름은 `게임 오버`{:class="block3myblocks"} 로 합니다.

\--- /task \---

\--- task \---

`빨간색`{:class="block3events"} 브로드 캐스트에 연결된 `아니면`{:class="block3control"} 블록의 코드를 `게임 오버`{:class="block3myblocks"} 블록에 추가합니다. 그럼, 다음과 같이 됩니다.

![발레리나](images/ballerina.png)

```blocks3
define Game over
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---

\--- task \---

`빨간색`{:class="block3events"} 브로드 캐스트에 연결된 `아니면`{:class="block3control"} 블록의 코드를 삭제하고 `게임 오버`{:class="block3myblocks"} 블록을 추가합니다:

![발레리나](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \---

게임을 플레이하고 색상 순서의 잘못된 지점에서 빨간색 버튼을 클릭하여 새 블록을 테스트 합니다.

\--- /task \---

새로운 `게임 오버`{:class="block3myblocks"} 블록은 **함수입니다.**, `게임 오버`{:class="block3myblocks"} 블록을 코드 원하는 곳에 추가하여 코드에서 어디에서나 사용할 수있는 스크립트입니다.

\--- task \---

다른 색상도 `브로드캐스트`{:class="block3events"}에 연결된 `아니면`{:class="block3control"} 블록을 새로운 `게임 오버`{:class="block3myblocks"} 블록으로 대체합니다. `파란색`{:class="block3events"} 메시지의 코드는 다음과 같습니다.

![발레리나](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \---

이제 잘못된 버튼을 눌렀을 때 재생되는 사운드를 추가합니다. 이 코드는 만든 `게임 오버`{:class="block3myblocks"} 블록에 한 번만 추가하면됩니다.

![발레리나](images/ballerina.png)

```blocks3
define Game over
start sound [Cough1 v]
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    play sound (trumpet1 v)
    set [high score v] to (score)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---