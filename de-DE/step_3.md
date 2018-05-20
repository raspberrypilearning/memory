## Zufällige Farben

Lass uns zunächst einen Charakter erstellen, der eine zufällige Reihenfolge an unterscheidlichen Farben annehmen kann, die sich der Spieler merken muss.

+ Starte ein neues Scratch-Projekt und lösche die Katzenfigur, so dass Dein Projekt leer ist. Du findest das Scratch-Bearbeitungsprogramm online auf jumpto.cc/scratch-new.

+ Füge eine neue Figur, sowie den passeden Bühnenhintergrund hinzu. Dein Charakter muss keine Person sein, aber er muss verschiedene Farben annehmen können.

![screenshot](images/colour-sprite.png)

+ Du wirst im Spiel unterschiedliche Zahlen für die jeweiligen Farben benutzen:
    
    + 1 = rot
    + 2 = blau
    + 3 = grün
    + 4 = gelb
    
    Gib Deinem Charakter vier unterschiedlich farbige Kostüme in den obigen Farben. Stelle sicher, dass die Farben der Kostüme richtig geordnet sind.
    
    ![screenshot](images/colour-costume.png)
    
    Du kannst mit der * -Farbe eine Form einfärben * Werkzeug, um Teile des Kostüms eine andere Farbe zu füllen.

Lässt uns eine zufällige Abfolge von Farben erstellen.

+ Erstelle eine neue Liste namens `Sequenz`{:class="blockdata"}. We will use this list to store the sequence of colours the player has to remember. Only the character sprite needs to see the list, so you can select **For this sprite only**.

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