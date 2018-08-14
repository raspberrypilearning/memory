## Creează o secvenţă de culori

În primul rând, haide să creăm un personaj care poate să afișeze la întâmplare o secvență de culori pentru ca un jucător să o memoreze.

+ Începe un nou proiect Scratch și șterge sprite-ul pisică. Poți găsi editorul de Scratch online [aici](http://jumpto.cc/scratch-new).

+ Alege un personaj și un fundal. Personajul tău nu trebuie să fie o persoană, dar trebuie să poată afișa culori diferite.

![screenshot](images/colour-sprite.png)

+ In your game, you'll use a different number to represent each colour:
    
    + 1 = red
    + 2 = blue
    + 3 = green
    + 4 = yellow
    
    Give your character four different coloured costumes, one for each of the four colours above. Make sure that your coloured costumes are in the same order as the list above.
    
    ![screenshot](images/colour-costume.png)
    
    You can use the *color a shape* tool to fill parts of the costume a different colour.

Let's create a random sequence of colours.

+ Create a list called `sequence`{:class="blockdata"}. We will use this list to store the sequence of colours the player has to remember. Only the character sprite needs to see the list, so you can select **For this sprite only**.

[[[generic-scratch-make-list]]]

You should now see your empty list in the top left of your stage, as well as lots of new blocks for using lists.

![screenshot](images/colour-list-blocks.png)

+ Remember we gave each colour a number? We can choose a random colour by choosing a random number and adding it to the list. Add this code:

```blocks
when flag clicked
add (pick random (1) to (4)) to [sequence v]
```

+ Test your code by clicking the green flag. Check that, each time you click it, a random number between 1 and 4 is added to the list.

+ Can you add this block to your program to generate five random colours at once?

```blocks
repeat (5)

end
```

+ You might notice that your list is getting a bit full by now. Let's add a block to delete the whole list at the start before we generate any numbers.

```blocks
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
end
```

+ Finally, each time we choose a number, let's change the dancer's costume to the last item that was added to the list, which will be the number we just chose. Add these blocks to your code immediately after you add the random number to your list:

```blocks
switch costume to (item (last v) of [sequence v])
wait (1) secs
```