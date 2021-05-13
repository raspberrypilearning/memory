## 순서 반복

이제 사용자가 색 시퀀스를 반복하기 위해 누를 4개의 버튼을 추가해야 합니다.

\--- task \---

4개의 버튼을 표시하기 위해 프로젝트에 새로운 스프라이트 4개를 추가하세요.

+ 네 가지 색상 각각에 하나의 스프라이트가 되도록 새로운 스프라이트의 의상을 편집하세요
+ 스프라이트를 의상과 같은 순서로 무대에 올려 놓으세요: 빨간색, 파란색, 초록색, 노란색

![스크린샷](images/colour-drums.png)

\--- /task \---

\--- task \---

빨간색 스프라이트에 아래와 같은 코드를 추가해 스프라이트가 클릭되었을 때 '빨간색' 메시지를 `방송하기`{:class="block3events"} 할 수 있도록 하세요.

![레드 드럼](images/red_drum.png)

```blocks3
    when this sprite clicked
    broadcast (red v)
```

\--- /task \---

`방송하기`{:class="block3events"} 는 아주 큰 스피커로 발표되는 메시지와 같으며, 예를 들어 학교나 슈퍼마켓 등에 설치된 스피커를 뜻합니다. 모든 스프라이트는 `방송하기`{:class="block3events"} 의 메시지를 들을 수 있지만, 응답해야 하는 스프라이트 만이 무언가를 수행할 것입니다.

\--- task \---

자신의 색깔에 대해서 메시지를 `방송하기`{:class="block3events"}할 수 있도록 파란색, 녹색, 노란색 드럼에 같은 코드를 추가하십시오.

\--- /task \---

`방송하기`{:class="block3events"} 는 아주 큰 스피커에서 나오는 메시지와 같다는 것을 기억하시나요? 캐릭터가 `방송하기`{:class="block3events"}의 메시지에 응답할 수 있도록 캐릭터에게 코드를 추가할 것입니다.

\--- task \---

캐릭터 스프라이트가 `빨간색`{:class="block3events"} 메시지를 받으면, 코드는 숫자`1`이 `순서`{:class=“block3variables”} 리스트의 처음에 있는지 여부를 확인합니다 (이는 `빨간색`{:class="block3events"}이 순서에서 다음 색이라는 것을 의미합니다).

만약 `1` 이 리스트의 시작이라면, 플레이어는 정확한 컬러를 기억했기 때문에 프로그램은 숫자를 리스트에서 삭제해야 합니다. 그렇지 않으면 게임이 종료되고 코드는 게임을 종료하기 위해 `멈추기 모두`{:class="block3control"} 블록을 사용합니다.

![발레리나](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end
```

\--- /task \---

\--- task \---

캐릭터 스프라이트가 올바른 `방송하기`{:class="block3events"}를 받을 때 드럼 비트도 재생할 수 있도록 방금 작성한 코드에 추가하세요.

\--- hints \---

\--- hint \---

드럼을 바르게 연주하기 위해서 각 색깔에 해당하는 숫자를 사용할 수 있나요?

+ 1 = 빨간색
+ 2 = 파란색
+ 3 = 초록색
+ 4 = 노란색

\--- /hint \---

\--- hint \---

`1의 항목을 모두 삭제하기`{:class="block3variables"} 블록 위에, `드럼 재생`{:class="block3sound"} 블록을 추가하여 `시퀀스`{:class="block3variables"} 에 해당하는 첫 번째 음악을 출력할 수 있도록 하세요.

\--- /hint \---

\--- hint \---

필요한 코드는 다음과 같습니다:

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then

+ play drum (\(1\) Snare Drum v) for (0.25) beats
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

스프라이트가 방송하기`빨간색`{:class="block3events"} 에 응답하도록 하는 코드를 복사하세요. 이번에는 메시지를 `파란색`{:class="block3events"} 으로 변경하세요.

\--- /task \---

스프라이트가 `파란색`{:class="block3events"} 메시지에 응답할 때 어떤 코드가 동일하게 유지되어야 하고, 어떤 비트가 변경되어야 할까요? 각 색상에는 해당 숫자가 있다는 것을 기억하십시오.

\--- task \---

캐릭터가 `파란색`{:class="block3events"} 메시지에 올바르게 응답하도록 스프라이트의 코드를 변경합니다.

\--- hints \---

\--- hint \---

이 블록을 유지하되 어떤 방식으로든 변경해야합니다.

![발레리나](images/ballerina.png)

```blocks3
<(item (1 v) of [sequence v]) = [1]>

when I receive [red v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

\--- /hint \---

\--- hint \---

다음은 코드가 `파랑`{:class="block3events"} 브로드 캐스트를 찾는 방법입니다.

![발레리나](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[2]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    stop [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

코드를 다시 복제하고 (초록색 및 노란색 버튼) 필요한 부분을 변경하여 캐릭터가 새로운 `방송하기`{:class="block3events"} 에 응답하도록 합니다.

\--- /task \---

코드를 테스트하는 것을 잊지 마십시오! 다섯 가지 색상의 순서를 외울 수 있습니까? 매번 순서가 다를까요?

When the player repeats the whole colour sequence correctly, the `sequence`{:class="block3variables"} list is empty and the player wins. 원한다면 `시퀀스`{:class="block3variables"} 리스트가 비어 있다면 깜빡이는 불빛을 보상으로 표시할 수 있습니다.

\--- task \---

이 코드를 풍선의 `깃발을 클릭했을 때`{:class="block3events"} 코드 가장 위쪽에 추가하세요:

![발레리나](images/ballerina.png)

```blocks3
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
```

\--- /task \---

\--- task \---

스테이지로 전환하고 `드럼 머신` 사운드 또는 원하는 다른 사운드를 가져옵니다.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \---

이 코드를 추가하여 사운드를 재생하고 플레이어가 이길 때 배경색을 변경합니다.

![발레리나](images/stage.png)

```blocks3
    when I receive [won v]
    start sound (drum machine v)
    repeat (50)
        change [color v] effect by (25)
        wait (0.1) seconds
    end
    clear graphic effects
```

\--- /task \---