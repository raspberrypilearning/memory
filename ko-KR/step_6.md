## 높은 점수

이제 높은 점수를 저장하여 친구들과 놀 수 있습니다.

\--- task \---

Add two new variables called `high score`{:class="block3variables"} and `name`{:class="block3variables"} to your project.

\--- /task \---

When the game ends because the player gets the sequence wrong, the game should check whether the score is higher than the current high score. If it is, the game should save the score as the high score, and also store the name of the player.

\--- task \---

Add code to your character sprite to store the `high score`{:class="block3variables"}. Also ask for the player's name, and store it in the `name`{:class="block3variables"} variable.

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

Your new code needs to follow this pattern:

After the `Game over`{:class="block3looks"} message `If`{:class="block3control"} the `score`{:class="block3variables"} is `greater than`{:class="block3operators"} the `high score`{:class="block3variables"} `Set`{:class="block3variables"} the `high score`{:class="block3variables"} to the `score`{:class="block3variables"} `Ask`{:class="block3sensing"} for the player's name `Set`{:class="block3variables"} the `name`{:class="block3variables"} to the `answer`{:class="block3sensing"}

\--- /hint \---

\--- hint \---

You need the following blocks:

![ballerina](images/ballerina.png)

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

\--- /hint \---

\--- hint \---

Here's how your code for when the red button is pressed should look:

![ballerina](images/ballerina.png)

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

\--- /hint \---

\--- /hints \---

\--- /task \---

You need to add this new code to the character sprite for the other three colours too!

Can you see that the 'Game over' code for each of the four colours is exactly the same?

![ballerina](images/ballerina.png)

```blocks3
[게임 오버!] (1 초) 동안
 < (점수 :: 변수) > (높은 점수) > 다음
    세트 [높은 점수 v] (점수 :: 변수)
    [높은 점수! 당신의 이름은 무엇입니까?] 그리고 기다림
    [이름 v]를 (답)

종료 [모두 v]
```

If you need to change any of the 'Game over' code, for example to add a sound or change the 'Game over' message, you have to change it four times. That's annoying and wastes a lot of time.

Instead, you can define your own code block, and use it anywhere in your project.

\--- task \---

Click on `My blocks`{:class="block3myblocks"}, and then on **Make a Block**. Call this new block `Game over`{:class="block3myblocks"}.

\--- /task \---

\--- task \---

Add the code from the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast to the `Game over`{:class="block3myblocks"} block so that it looks like this:

![ballerina](images/ballerina.png)

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

\--- task \---

Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

![ballerina](images/ballerina.png)

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

\--- task \---

Test your new block by playing the game and clicking the red button at the wrong point in the colour sequence.

\--- /task \---

Your new `Game over`{:class="block3myblocks"} block is a **function**, a little script that you can use anywhere you like in your code by adding the `Game over`{:class="block3myblocks"} block in.

\--- task \---

Also replace the code in the `else`{:class="block3control"} block connected to the `broadcasts`{:class="block3events"} for the other colours with your new `Game over`{:class="block3myblocks"} block. Here is what the code for the `blue`{:class="block3events"} message should look like

![ballerina](images/ballerina.png)

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

\--- task \---

Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.png)

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