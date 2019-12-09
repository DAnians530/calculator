----------
Davey Devs
- Calculator I made without looking at any tutorials

I got it to work, somehow, and am feeling pretty proud. Obviously, without any tutorials, it's a bit messy and has lots of room for improvement. 
-------------

Helpful links used to make this work:

parseInt/parseFloat (I used parseFloat): https://gomakethings.com/converting-strings-to-numbers-with-vanilla-javascript/

.join: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join


------------------
How I got it to work:

1. Differentiated numbers (and decimal/negative) from operators (+, -, *, /)

2. Created individual variables for all numbers and operators.

3. Created variables for the logic:
	- An array with "a" and "b", used to help know which part of the operation we're at.
	- An array called "answer", with a length of 3, starting off blank, to be filled with the 1st number, the operator, and the 2nd number.
	- An answer string variable where the answer will go and then be put in the display.

4. Created a start/reset function attached to the button

5. Had all numbers and operators go to the same function when clicked, and then used switch and if/else conditions to narrow down:
	- Case for which number or operator it is, then:
		- If it's a number or decimal/negative sign, whether we're in the first or second half of the equation (a or b).
			- Then adds to the string for the number, to be later converted to a float. 
		- When an operator is clicked, the first time, it switches from a to b, and allows us to start choosing the second number, and then puts the operator in the answer array. 
		- If the equals button OR an operator when we already have one: step 6!

6! Create variables to join the 1st number and 2nd number strings, then use parseFloat to change them from strings to numbers you can do math on.


7. Another switch to see which operator was selected earlier, in order to:
	- Do math with javascript using the selected numbers and operator
	- Show the answer in the innerHTML of the display
	- Make the answer the new first element of the length 3 array we assembled, and make the other spots blank
		- This prepares for us to continue calculating with the answer instead of completely resetting.
	- Reset our a,b variable to show that we're ready to continue.

8. Now any numbers and operators chosen can continue to calculate on the previous answers, until we reset or try a buggy number (usually caused by misplaced negative signs or decimals)



----------------
Obvious issues/bugs:

- Need to make CSS responsive, especially in landscape

- It was going slow on mobile, but now it isn't. Not sure what I did right or wrong?

- "NaN" whenever things aren't entered right, which is fine, but you need to clear in order to continue or else it says on screen.  Probably an easy fix. 

- Need to make more accessible. 
	- How to tab to the answer
	- Make sure the tab order isn't confusing
	- Figure out what alt text would be needed