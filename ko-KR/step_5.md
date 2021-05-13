## 여러 단계

지금까지 플레이어는 5가지 색상 순서 만 기억하면됩니다. 점수를 추가하고 플레이어가 점수를 매기면서 게임이 다음 단계로 이동하고 기억할 색상 순서가 길어 지도록 코드를 추가하여 게임을 개선하세요.

\--- task \---

먼저, `점수`{:class="block3variables"}라는 이름의 새 변수를 추가 해 보세요.

[[[generic-scratch3-add-variable]]]

\--- /task \---

`점수`{:class="block3variables"} 에 기반하여, 게임은 색상 시퀀스의 길이를 결정합니다. `3`점으로 시작합니다.

\--- task \---

`깃발을 클릭했을때`{:class="block3events"} 를 클릭하면 `점수`{:class="block3variables"} 가 `3`이 되도록 캐릭터에 코드를 추가하세요.

\--- /task \---

항상 5가지 색상의 시퀀스를 생성하는 대신 `점수`{:class="block3variables"}가 시퀀스 길이를 결정하기를 원합니다.

\--- task \---

캐릭터의 `반복하기`{:class="block3control"} 루프를 (컬러 시퀀스 제작용) `점수`{:class="block3variables"} 만큼 반복하도록 변경합니다:

![스프라이트](images/ballerina.png)

```blocks3
repeat (score :: variables)
end
```

\--- /task \---

\--- task \---

플레이어가 올바른 시퀀스를 반복하면 `1` 이 `score`{:class="block3variables"}에 더해져야 하며, 이렇게 하면 다음 시퀀스의 길이가 늘어납니다. 캐릭터 코드에 다음을 추가하여 **시퀀스가 올바른지 알 수 있도록 하세요.**:

![스프라이트](images/ballerina.png)

```blocks3
change [score v] by (1)
```

\--- hints \---

\--- hint \---

게임이 `방송하기`{:class="block3events"} 를 통해 '승리' 메시지를 방송할 때 시퀀스가 정확함을 알 수 있습니다.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

마지막으로 시퀀스를 생성하는 코드 주위에 `무한 반복`{:class="block3control"} 루프를 추가하여 게임이 각 레벨에 대해 새로운 색상 시퀀스를 생성하도록합니다. 캐릭터의 코드는 다음과 같을 것입니다:

![발레리나](images/ballerina.png)

```blocks3
when flag clicked
set [score v] to [3]
forever
    delete (all v) of [sequence v]
    repeat (score)
        add (pick random (1) to (4)) to [sequence v]
        switch costume to (item (length of [sequence v]) of [sequence v]
        wait (1) seconds
    end
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
    change [score v] by (1)
end
```

\--- /task \---

\--- task \---

친구들이 게임을 테스트하도록하세요. `시퀀스`{:class="block3variables"} 목록을 재생하기 전에 숨기는 것을 잊지 마십시오!

\--- /task \---