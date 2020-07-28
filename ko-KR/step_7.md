## 도전과제: 더 멋진 게임 만들기

### 더 많은 블록 만들기

4 개의 버튼 모두에 대해 다른 코드가 보이나요?

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game Over :: custom
end

when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

모든 버튼에서 사용할 수 있는 다른 사용자 정의 블록을 만들 수 있습니까?

### 다른 의상

캐릭터가 네 가지 색상 중 하나를 나타내는 것으로 게임이 시작되고 플레이어가 색상 순서를 반복하는 동안 캐릭터가 항상 순서의 마지막 색상을 표시한다는 것을 알 수 있습니까?

Can you add another plain white costume to your character, and add code so that the character displays this costume at the start of the game and while the player is repeating the sequence?

![스크린샷](images/colour-white.png)

### 난이도

플레이어가 게임을 '쉬운 모드'(빨간색과 파란색 만 사용) 와 '일반 모드'(4 가지 색상 모두 사용) 중에서 선택하도록 할 수 있습니까?

다섯 번째 드럼을 사용하는 '어려운' 모드를 추가할 수도 있습니다!