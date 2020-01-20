## 사운드 추가

\--- task \---

프로젝트를 몇 번 테스트하십시오. 때로는 동일한 번호가 두 번 (또는 그 이상) 연속적으로 선택된다는 것을 알기 때문에 시퀀스를 암기하기가 더 어려워 집니까?

\--- /task \---

캐릭터 스프라이트가 의상을 바꿀 때마다 드럼 사운드를 재생할 수 있습니까? 그리고 각 색상마다 다른 드럼 사운드가 어때요?

\--- task \---

뮤직 확장을 프로젝트에 추가하여 `play drum`{: class = "block3extensions"} 블록을 사용할 수있게하십시오.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

드럼을 연주하는 코드는 **매우** 캐릭터의 의상을 변경하는 코드와 유사.

\--- hints \---

\--- hint \---

You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block.

\--- /귀뜸말 \---

\--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
[시퀀스 v]의

(항목 ([시퀀스 v] 길이)을 ( 

 )에 대해 스누핑 드럼 (\ (1 \) 스네어 드럼 v)
```

\--- /hint \---

\--- hint \---

Here is how your finished code should look:

![ballerina](images/ballerina.png)

```blocks3
(시퀀스 v)의
삭제 (모든 v)
repeat (5)
    add (select random (1) to (4))
    [ (시퀀스 v)의 길이 ([시퀀스 v]의 길이)에 대한
    스위치 코스튬을 상쇄한다
    대기 (1) 초
끝
```

\--- /hint \---

\--- /hints \---

\--- /task \---