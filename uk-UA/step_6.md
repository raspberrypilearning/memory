# High score

Now save the high score so that you can play against your friends.

\--- task \--- Add two new variables called `high score`{:class="block3variables"} and `name`{:class="block3variables"} to your project. \--- /task \---

When the game ends because the player gets the sequence wrong, the game should check whether the score is higher than the current high score. If it is, the game should save the score as the high score, and also store the name of the player.

\--- task \--- Add code to your character sprite to store the `high score`{:class="block3variables"}. Also ask for the player's name, and store it in the `name`{:class="block3variables"} variable.

[[[generic-scratch3-high-score]]]

\--- hints \--- \--- hint \--- Your new code needs to follow this pattern:

After the `Game over`{:class="block3looks"} message `If`{:class="block3control"} the `score`{:class="block3variables"} is `greater than`{:class="block3operators"} the `high score`{:class="block3variables"} `Set`{:class="block3variables"} the `high score`{:class="block3variables"} to the `score`{:class="block3variables"} `Ask`{:class="block3sensing"} for the player's name `Set`{:class="block3variables"} the `name`{:class="block3variables"} to the `answer`{:class="block3sensing"} \--- /hint \--- \--- hint \---

You need the following blocks:

![ballerina](images/ballerina.png)

![blocks_1545306917_8757622](images/blocks_1545306917_8757622.png) \--- /hint \--- \--- hint \--- Here's how your code for when the red button is pressed should look:

![ballerina](images/ballerina.png)

![blocks_1545306919_0175269](images/blocks_1545306919_0175269.png) \--- /hint \--- \--- /hints \--- \--- /task \---

You need to add this new code to the character sprite for the other three colours too!

Can you see that the 'Game over' code for each of the four colours is exactly the same?

![ballerina](images/ballerina.png)

![blocks_1545306920_1657844](images/blocks_1545306920_1657844.png)

If you need to change any of the 'Game over' code, for example to add a sound or change the 'Game over' message, you have to change it four times. That's annoying and wastes a lot of time.

Instead, you can define your own code block, and use it anywhere in your project.

\--- task \--- Click on `My blocks`{:class="block3myblocks"}, and then on **Make a Block**. Call this new block `Game over`{:class="block3myblocks"}.

\--- /task \---

\--- task \--- Add the code from the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast to the `Game over`{:class="block3myblocks"} block so that it looks like this:

![ballerina](images/ballerina.png)

![blocks_1545306921_3138576](images/blocks_1545306921_3138576.png) \--- /task \---

\--- task \--- Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

![ballerina](images/ballerina.png)

![blocks_1545306922_4493077](images/blocks_1545306922_4493077.png) \--- /task \---

\--- task \--- Test your new block by playing the game and clicking the red button at the wrong point in the colour sequence. \--- /task \---

Your new `Game over`{:class="block3myblocks"} block is a **function**, a little script that you can use anywhere you like in your code by adding the `Game over`{:class="block3myblocks"} block in.

\--- task \--- Also replace the code in the `else`{:class="block3control"} block connected to the `broadcasts`{:class="block3events"} for the other colours with your new `Game over`{:class="block3myblocks"} block. Here is what the code for the `blue`{:class="block3events"} message should look like

![ballerina](images/ballerina.png)

![blocks_1545306923_5727518](images/blocks_1545306923_5727518.png) \--- /task \---

\--- task \--- Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.png)

![blocks_1545306924_6780515](images/blocks_1545306924_6780515.png) \--- /task \---