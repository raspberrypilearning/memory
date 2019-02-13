## 높은 점수

이제 높은 점수를 저장하여 친구들과 놀 수 있습니다.

\--- task \--- `높은 점수`{: class = "block3variables"}와 `이름`{: class = "block3variables"}라는 두 개의 새로운 변수를 프로젝트에 추가하십시오. \--- / task \---

플레이어가 시퀀스가 잘못되어 게임이 끝나면 게임은 현재 높은 점수보다 높은 점수인지 확인해야합니다. 그렇다면 게임은 점수를 높은 점수로 저장해야하며 플레이어의 이름도 저장해야합니다.

\--- task \--- `높은 점수`{{class = "block3variables"}를 저장하기 위해 캐릭터 스프라이트에 코드를 추가하십시오. 또한 플레이어의 이름을 물어보고 `name`{: class = "block3variables"} 변수에 저장하십시오.

[[[generic-scratch3-high-score]]]

\--- 힌트 \--- \--- 힌트 \--- 새로운 코드는이 패턴을 따라야합니다 :

애프터 `게임 위에`{CLASS = "block3looks"} 메시지 `의 경우`{CLASS = "block3control"}를 `점`{CLASS = "block3variables"}를 `이상`클래스 = "block3operators { "}는 `고득점`{CLASS ="block3variables "} `세트`{CLASS ="block3variables "}을 `고득점`{CLASS ="block3variables의 "로} `골`{CLASS =" block3variables "} `질문`{: 클래스 ="block3sensing "플레이어의 이름} `세트`{: 클래스 ="block3variables "}는 `명`{: 클래스 ="받는 block3variables "} `답`{: class = "block3sensing"} \--- / 힌트 \--- \--- 힌트 \---

다음 블록이 필요합니다.

![발레리나](images/ballerina.png)

```blocks3
< > 점
점

점

점

점 > 점

점

점

점

점 [높은 점수 v] ~ [ 

점] 이름 v]를 [] 
```

\--- / 힌트 \--- \--- 힌트 \--- 다음은 빨간 버튼을 눌렀을 때의 코드입니다 :

![발레리나](images/ballerina.png)

```blocks3
I는 [적색 V] 나타나면
경우 <(항목 (1 V) [서열 V]의) =[1]> 다음,
    (0.25) 심박동 재생 드럼 (항목 (1 V) [서열 V]로)
    삭제 (1 V) [서열 V]의
다른
    말 [위에 게임!] (1) 초
    의 경우 < (점수 : 변수) > (고득점) > 다음,
        (점수 : 변수 집합 [고득점 V] )
        [높은 점수! 당신의 이름은 무엇입니까?]
        기다림 [이름 v]를 (답)
    끝
    멈춤 [모두 끝]
끝
```

\--- / 힌트 \--- \--- / 힌트 \--- \--- / 작업 \---

다른 세 가지 색상에 대해서도이 새로운 코드를 문자 스프라이트에 추가해야합니다!

네 가지 색상 각각에 대한 '게임 오버'코드가 정확히 동일하다는 것을 알 수 있습니까?

![발레리나](images/ballerina.png)

```blocks3
[게임 오버!] (1 초) 동안
 < (점수 :: 변수) > (높은 점수) > 다음
    세트 [높은 점수 v] (점수 :: 변수)
    [높은 점수! 당신의 이름은 무엇입니까?] 그리고 기다림
    [이름 v]를 (답)

종료 [모두 v]
```

예를 들어 사운드를 추가하거나 'Game Over'메시지를 변경하는 것과 같은 'Game Over'코드를 변경해야하는 경우 4 번 변경해야합니다. 그것은 짜증나고 많은 시간을 낭비합니다.

대신 자신 만의 코드 블록을 정의하여 프로젝트의 어느 곳에서나 사용할 수 있습니다.

\--- 작업 \--- 을 클릭 `내 블록`{: 클래스 = "block3myblocks"}, 다음에 **블록 확인**. 이 새로운 블록을 호출하십시오 `Game over`{: class = "block3myblocks"}.

\--- /task \---

\--- task \--- `게임 오버`{{class = "block3events"} 브로드 캐스트 된 `빨간색`{: class = "block3control"} 블록에 연결된 `else`{: class = "block3control"} 블록의 코드를 추가합니다. "block3myblocks"} 블록으로 다음과 같이 보입니다 :

![발레리나](images/ballerina.png)

```blocks3
이상 게임을 정의
말 [이상 게임!] (1) 초
경우 < (점수 : 변수) > (높은 점수) > 다음
    (점수 : 변수)에 세트 [높은 점수 V]가
    질문 [높은 점수 ! 당신의 이름은 무엇입니까?] 그리고 기다림
    [이름 v]를 (답)

종료 [모두 v]
```

\--- /task \---

\--- task \--- 이제 `빨간색`{: class = "block3events"} 브로드 캐스트에 연결된 `else`{: class = "block3control"} 블록에있는 코드를 제거하고 `Game Over`{: class = "block3myblocks"} 대신 블록 :

![발레리나](images/ballerina.png)

```blocks3
I는 [적색 V] 나타나면
경우 <(항목 (1 V) [서열 V]의) =[1]> 다음
    재생 드럼 (\ (1 \)은 스네어 드럼 V) (0.25)에 대한 박동
    삭제 (1 V) [시퀀스 v]
else
    게임 오버 : : 사용자 정의
끝
```

\--- /task \---

\--- task \--- 게임을하고 색상 순서의 잘못된 지점에서 빨간 버튼을 클릭하여 새 블록을 테스트하십시오. \--- / 작업 \---

새로운 `Game over`{: class = "block3myblocks"} 블록은 **함수**.</code>{{class = "block3myblocks"}} 블록을 통해 `Game을 추가하여 코드에서 원하는 곳이면 어디든 사용할 수있는 작은 스크립트입니다. 에서.</p>

<p>--- task ---
 <code>브로드 캐스트`{{class = "block3events"}에 연결된 `else`{: class = "block3control"} 블록의 코드를 새 `Game Over로 다른 색상으로 대체하십시오`{: class = "block3myblocks"} 블록. 다음은 `파란색`{: class = "block3events"} 메시지의 코드입니다.

![발레리나](images/ballerina.png)

```blocks3
I는 [블루 V] 나타나면
경우 <(항목 (1 V) [서열 V]의) =[1]> 다음
    재생 드럼 (\ (2 \)은베이스 드럼 V) (0.25)에 대한 박동
    삭제 (1 V) [시퀀스 v]
else
    게임 오버 : : 사용자 정의
끝
```

\--- /task \---

\--- task \--- 잘못된 버튼을 누르면 소리가납니다. 당신은 단지 한 번이 코드를 추가 할 필요가 `이상 게임`{: 클래스 = "block3myblocks"} 블록 당신이 만든, 그리고 네 개의 개별 번!

![발레리나](images/ballerina.png)

```blocks3
게임 오버를 정의
시작 음 [Cough1의 V]
(1) 초 [위에 게임!] 말
의 경우 < (점수 : 변수) > (고득점) > 다음
    소리 재생 (trumpet1의 V)
    세트 [고득점 v] ~ (score)
    [높은 점수! 당신의 이름은 무엇입니까?] 그리고 기다림
    [이름 v]를 (답)

종료 [모두 v]
```

\--- /task \---