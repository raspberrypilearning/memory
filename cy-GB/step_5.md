## Lefelau gwahanol

Hyd yn hyn, mae’r chwareuwr ond wedi gorfod cofio 5 lliw. Beth am wella’r gêm trwy ychwanegu sgôr, ac ychwanegu côd fel bod y chwareuwr yn ennill pwyntiau, y gêm yn symud i'r lefel nesaf a'r dilyniant lliwiau i'w gofio yn cynyddu.

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
ailadrodd (sgôr :: variables)
end
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
newid [sgôr v] gan (1)
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
pan fo'r flag werdd yn cael ei glicio
gosod [sgôr v] i [3]
am byth 
  dileu (all v) o [dilyniant v]
  ailadrodd (sgôr) 
    ychwanegu (dewis ar hap (1) i (4)) i [dilyniant v]
    newid gwisg i (eitem (hyd [dilyniant v]) o [dilyniant v])
    aros (1) eiliad
  end
  aros hyd at <(hyd [dilyniant v]) = [0]>
  darlledu (won v) ac aros
  newid [sgôr v] gan (1)
end
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---