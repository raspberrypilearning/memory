## 여러 단계

지금까지 플레이어는 5 가지 색상 순서 만 기억하면됩니다. 점수를 추가하고 플레이어가 점수를 매기면서 게임이 다음 단계로 이동하고 기억할 색상 순서가 길어 지도록 코드를 추가하여 게임을 개선하십시오.

\--- task \---

Create a new variable called `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

Based on the `score`{:class="block3variables"}, the game will decide on the length of the colour sequence. Start with a score (and a sequence length) of `3`.

\--- task \---

Add a block at the start of your character's `when flag clicked`{:class="block3events"} code to set the `score`{:class="block3variables"} to `3`.

\--- /task \---

Instead of always creating a sequence of five colours, you now want the `score`{:class="block3variables"} to determine the sequence length.

\--- task \---

Change the character's `repeat`{:class="block3control"} loop (for creating the colour sequence) to repeat `score`{:class="block3variables"} times:

![sprite](images/ballerina.png)

```blocks3
반복 (score :: variables)
끝
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
[점수 v]를 (1)
```

\--- hints \---

\--- hint \---

You know the sequence is correct at the point when the game `broadcasts`{:class="block3events"} the 'win' message.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Finally, add a `forever`{:class="block3control"} loop around the code that generates the sequence, so that the game creates a new colour sequence for each level. This is how your character's code might look:

![ballerina](images/ballerina.png)

```blocks3
플래그가 클릭하면
으로 세트 [점수 절] [3]
영원히
    (모든 V)의 [시퀀스 V] 삭제
    반복 (점수)
        추가 (선택 임의 (1) ~ (4))에 [순서 V]
        스위치 의상을 [서열 V]) 여기서 시퀀스 V]의 항목 (행 (길이
        의 대기 (1) 초
    단부
    대기까지 < ([서열 V) = 길이 [0]>
    방송 (원 V) 기다려
    [변경 점수 v] by (1)
end
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---