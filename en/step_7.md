## Challenge: changing the difficulty

### Making more blocks
Do you notice any other code that is the same for all four buttons?

```blocks
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (item (1 v) of [sequence v]) for (0.25) beats
	delete (1 v) of [sequence v]
else
	Game Over :: custom
endp

when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (item (1 v) of [sequence v]) for (0.25) beats
	delete (1 v) of [sequence v]
else
	Game over :: custom
end
```

Can you make another custom block for each button to use?

### Another costume
Have you noticed that your game starts with your character showing one of the four colours, and that they always display the last colour in the sequence while the player is repeating the sequence?

Can you add another plain white costume to your character, which is displayed at the start of your game, and when the player is trying to copy the sequence?

![screenshot](images/colour-white.png)

### Difficulty level
Can you allow your player to choose between 'easy mode' (using just the red and blue drums) and 'normal mode' (which uses all four drums)?

You could even add a 'hard' mode, which makes use of a fifth drum!


