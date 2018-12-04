# High score

Now save the high score so that you can play against your friends.

--- task ---
Add two new variables called `high score`{:class="blockdata"} and `name`{:class="blockdata"} to your project.
--- /task ---

When the game ends because the player gets the sequence wrong, the game should check whether the score is higher than the current high score. If it is, the game should save the score as the high score, and also store the name of the player.

--- task ---
Add code to your character sprite to store the `high score`{:class="blockdata"}. Also ask for the player's name, and store it in the `name`{:class="blockdata"} variable.

[[[generic-scratch-high-score]]]

--- hints ---
--- hint ---
Your new code needs to follow this pattern:

After the `Game over`{:class="blocklooks"} message
`If`{:class="blockcontrol"} the `score`{:class="blockdata"} is `greater than`{:class="blockoperators"} the `high score`{:class="blockdata"}
`Set`{:class="blockdata"} the `high score`{:class="blockdata"} to the `score`{:class="blockdata"}
`Ask`{:class="blocksensing"} for the player's name
`Set`{:class="blockdata"} the `name`{:class="blockdata"} to the `answer`{:class="blocksensing"}
--- /hint ---
--- hint ---

You need the following blocks:

![ballerina](images/ballerina.png)

```blocks
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(high score)

ask [What's your name?] and wait

set [high score v] to [ ] 

set [name v] to [ ] 
```
--- /hint ---
--- hint ---
Here's how your code for when the red button is pressed should look:

![ballerina](images/ballerina.png)

```blocks
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (item (1 v) of [sequence v]) for (0.25) beats
	delete (1 v) of [sequence v]
else
	say [Game over!] for (1) secs
	if < (score) > (high score) > then
		set [high score v] to (score)
		ask [High score! What is your name?] and wait
		set [name v] to (answer)
	end
	stop [all v]
end
```
--- /hint ---
--- /hints ---
--- /task ---

You need to add this new code to the character sprite for the other three colours too!

Can you see that the 'Game over' code for each of the four colours is exactly the same?

![ballerina](images/ballerina.png)

```blocks
say [Game over!] for (1) secs
if < (score) > (high score) > then
	set [high score v] to (score)
	ask [High score! What is your name?] and wait
	set [name v] to (answer)
end
stop [all v]
```

If you need to change any of the 'Game over' code, for example to add a sound or change the 'Game over' message, you have to change it four times. That's annoying and wastes a lot of time.

Instead, you can define your own code block, and use it anywhere in your project.

--- task ---
Click on `More blocks`{:class="blockmoreblocks"}, and then on **Make a block**. Call this new block `Game over`{:class="blockmoreblocks"}.

--- /task ---

--- task ---
Add the code from the `else`{:class="blockcontrol"} block connected to the `red`{:class="blockevents"} broadcast to the `Game over`{:class="blockmoreblocks"} block so that it looks like this:

![ballerina](images/ballerina.png)

```blocks
define Game over
say [Game over!] for (1) secs
if < (score) > (high score) > then
	set [high score v] to (score)
	ask [High score! What is your name?] and wait
	set [name v] to (answer)
end
stop [all v]
```
--- /task ---

--- task ---
Now remove the code that's in the `else`{:class="blockcontrol"} block connected to the `red`{:class="blockevents"} broadcast, and add in the `Game over`{:class="blockmoreblocks"} block instead:

![ballerina](images/ballerina.png)

```blocks
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (item (1 v) of [sequence v]) for (0.25) beats
	delete (1 v) of [sequence v]
else
	Game over
end
```
--- /task ---

--- task ---
Test your new block by playing the game and clicking the red button at the wrong point in the colour sequence.
--- /task ---

Your new `Game over`{:class="blockmoreblocks"} block is a __function__, a little script that you can use anywhere you like in your code by adding the `Game over`{:class="blockmoreblocks"} block in.

--- task ---
Also replace the code in the `else`{:class="blockcontrol"} block connected to the `broadcasts`{:class="blockevents"} for the other colours with your new `Game over`{:class="blockmoreblocks"} block. Here is what the code for the `blue`{:class="blockevents"} message should look like

![ballerina](images/ballerina.png)

```blocks
when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (item (1 v) of [sequence v]) for (0.25) beats
	delete (1 v) of [sequence v]
else
	Game over
end
```
--- /task ---

--- task ---
Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="blockmoreblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.png)

```blocks
define Game over
play sound [cough-female v]
say [Game over!] for (1) secs
if < (score) > (high score) > then
	play sound [trumpet1 v]
	set [high score v] to (score)
	ask [High score! What is your name?] and wait
	set [name v] to (answer)
end
stop [all v]
```
--- /task ---
