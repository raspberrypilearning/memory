## 색상 순서 만들기

먼저 임의의 색상 순서를 표시 할 수있는 문자를 만듭니다.

\--- task \--- 새 Scratch 프로젝트를 엽니 다.

**Online**: open a new online Scratch project at [rpf.io/scratch-new](https://rpf.io/scratchon).

**오프라인**: 오프라인 편집기에서 새 프로젝트를 엽니 다.

Scratch 오프라인 편집기를 다운로드하여 설치해야하는 경우 [rpf.io/scratchoff](https://rpf.io/scratchoff)에서 찾을 수 있습니다.

\--- /task \---

\--- task \--- 문자 스프라이트와 배경을 선택하십시오. 발레리나를 사용할 수는 있지만 캐릭터가 사람 일 필요는 없으며 다른 색상 만 표시 할 수 있어야합니다.

![스크린샷](images/colour-sprite.png) \--- /task \---

+ 게임에서 각 색상을 나타내는 데 다른 숫자를 사용해야합니다.
    
    + 1 = 적색
    + 2 = 청색
    + 3 = 녹색
    + 4 = 노란색

\--- task \--- 당신의 성격에 색깔이 다른 네 가지의 의상, 위의 네 가지 색깔 각각에 대한 의상 하나를줍니다. 색깔있는 의상이 위 목록과 같은 순서인지 확인하십시오.

![스크린샷](images/colour-costume.png) \--- /task \---

원하는 경우 **색을 사용하여 모양** 도구를 사용하여 복장 부분을 다른 색으로 채울 수 있습니다.

![색깔 - 모양](images/color-a-shape.png)

다음으로, 플레이어가 기억해야하는 무작위 순서의 색을 저장하는 목록을 추가하십시오.

\--- task \--- `sequence`{: class = "block3variables"}라는 목록을 만듭니다. 문자 스프라이트 만이 목록을 볼 필요가 있으므로 **을 선택할 수 있습니다.이 스프라이트의 경우 목록을 만들 때** 선택하십시오.

[[[generic-scratch3-make-list]]]

\--- /task \---

이제 목록을 사용하기위한 새로운 코드 블록이 많이 표시됩니다. 빈 목록은 스테이지의 왼쪽 상단에 표시되어야합니다.

![스크린샷](images/colour-list-blocks-annotated.png)

각 색상마다 다른 숫자가 있으므로 번호를 임의로 선택하여 목록에 추가하여 임의의 색상을 선택할 수 있습니다.

\--- task \--- 이 코드를 문자 스프라이트에 추가하여 임의의 숫자를 선택하고 `추가하십시오. sequence`{: class = "block3variables"} :

![발레리나](images/ballerina.png)

```blocks3
깃발을 클릭할 때
랜덤 수 (1) ~ (4) 을 골라서 연속 V에 추가하세요.
```

\--- /task \---

\--- task \--- 코드를 테스트하십시오. 이 플래그를 클릭 할 때마다 1에서 4 사이의 임의의 숫자가 목록에 추가되는지 확인하십시오. \--- / 작업 \---

\--- task \--- 한 번에 5 개의 난수를 생성하는 코드를 프로그램에 추가 할 수 있습니까?

\--- 힌트 \--- \--- 힌트 \--- 추가합니다. `모든 시퀀스를 삭제합니다.`{: class = "block3variables"} 먼저 목록의 모든 항목을 삭제 한 다음 `반복을 추가합니다.`{: class = "block3control"} 5 개의 난수를 목록에 추가합니다. \--- / 힌트 \--- \--- 힌트 \---

이 코드는 다음과 같습니다.

![발레리나](images/ballerina.png)

```blocks3
깃발이  클릭 될 때
[연속  V] 의 모든 V  삭제
반복 (5)
    추가 ((1) ~ (4) 랜덤을 골라  [연속 V] 에 추가하십시오.
끝
```

\--- / 힌트 \--- \--- / 힌트 \--- \--- / task \---

\--- task \--- 숫자가 목록에 추가 될 때마다, 캐릭터는 복장의 색이 숫자와 일치하도록 복장을 변경해야합니다. 이 블록을 임의의 숫자가 `추가 된 바로 아래 코드에 삽입하십시오. sequence`{: class = "block3variables"} :

![발레리나](images/ballerina.png)

```blocks3
[시퀀스 v]의 (항목 (시퀀스 v)의 길이)로 복장을 바꾼다
대기 (1) 초
```

\--- /task \---