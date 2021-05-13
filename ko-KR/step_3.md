## 소리 추가

\--- task \---

프로젝트를 몇 번 테스트하십시오. 때로는 동일한 번호가 두 번 (또는 그 이상) 연속적으로 선택되고, 이것으로 인해 시퀀스를 암기하기가 더 어려워지는 것을 알았나요?

\--- /task \---

캐릭터 스프라이트가 의상을 바꿀 때마다 드럼 소리를 재생할 수 있습니까? 그리고 각 색상마다 다른 드럼 소리가 어때요?

\--- task \---

뮤직 확장을 프로젝트에 추가하여 `드럼 연주하기`{: class = "block3extensions"} 블록을 사용할 수 있게 하십시오.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

드럼을 연주하는 코드는 캐릭터의 의상을 변경하는 코드와 **매우** 유사합니다.

\--- hints \---

\--- hint \---

2개의 블록만 추가하면 됩니다: `드럼 타악기를 (0.25) 박자로 연주하기`{:class="block3sound"} 블록과 `(length of sequence) 리스트의 시퀀스 번째 항목`{:class="block3variables"} 블록을 추가합니다.

\--- /hint \---

\--- hint \---

필요한 코드 블록은 다음과 같습니다.

![발레리나](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

\--- /hint \---

\--- hint \---

코드는 다음과 같아야 합니다:

![발레리나](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
    play drum (item (length of [sequence v]) of [sequence v]) for (0.25) beats
    switch costume to (item (length of [sequence v]) of [sequence v])
    wait (1) seconds
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---