# Process Workshop Steps
This guide was written after receiving some great advice from Alice at Makers on how to do a process workshop or review. It's Ruby centric so that I could use real code examples to reinforce some of the ideas. You can still use the same process for another language but would have to substitute the code for your languages equivalent.

** Anything with two asterisks was a note from Alice. Alice drew out this process on a whiteboard and you can see that [here](https://github.com/bengscott2/process-review-steps/blob/master/Alice's%20Whiteboard%20Drawing.jpg)

** Make sure to keep talking through your process workshop/ review. It will help the reviewer understand what you’re doing

## Step 1 - PLANNING PHASE 1
* You may find it helpful to lay out all of your planning information below in a readme. You then can refer back to that while you build you program.
* Understand the requirements - During a review these requirements probably won't be given to you automatically. You will need to ask the reviewer these questions and set out the expectations yourself.
	* Who is the user?
		* Where does the expected output return to?
			* Command line?(```puts answer```)
			* Website? (**This won’t come up on a review**)
			* Only return to main? (```return answer```)
	* How do they use it?
		* What is the expected input (types)?
		* What is the expected output (types)?
		* Start building your input/output table
	* What is the acceptance criteria (examples)?
		* Given input: [input example here]
		* Output should be: [output example here]
	* What are some edge cases (examples)?
		* Given input: [input example here]
		* Output should be: [output example here]

<br>
* At this stage you should not be thinking about logic at all.
* You should be thinking about the program as a black box
* Plan out the simplest input/outputs and work from there

**Figure out what your first test will be and move on to step 2**


**At this point if you’ve spent too much time planning it may look like you’re afraid of starting to code and may not look great

** If you want to create a readme or initialise git at this point that’s fine but you should be explaining why you are or are not doing either of those things.

** If you do decide to create a readme don’t spend too much time on it. If you spend too much time on it may again look like you’re trying to avoid coding. At this point a title and your planning is enough. The readme can be updated as your program grows.

** If you decide to initialise git then now would be a good time to make your initial commit.

## Step 2 - WRITING SIMPLE TESTS
* Create your file system

	* ```bundle init```
	* add ```gem rspec``` to gemfile
	* ```bundle install```
	* ```rspec —init```

* Create your first spec file
	* ```touch spec/some_file_name_spec.rb```

* Start to write your first test
	* This should be the test that you’ve already decided as the easiest and most simple input/ output.
	* ```require``` your code file at the top of the spec file
	* Write your `describe` and `it` blocks
	* Watch your test fail.
	* There doesn't need to be any expects written at this point.
	* I like to have the test fail on requiring the file and let that drive me to creating the file.
	* ```mkdir lib```
	* ```touch lib/some_file_name.rb```
	* Run Rspec again
	* Follow the errors to create a class (if needed) and a method
	* You should run Rspec several times in that process, letting the error messages guide you
	* Once you stop getting errors you can move on to writing your first expect statement
	* Start out with the easiest input/ ouput
* Write your first bit of passing code
	* **If you need to write your program with a class, do so, but only if it’s necessary. In some of the process workshops for instance it shows you that the requirement doesn’t call for a class.**
	* To pass this test you will want to write the easiest bit of code to pass the test.
	* Generally that means hard coding the return that you’re looking for.
	* You could write something /slightly/ more complicated but you shouldn’t be tackling any forward thinking logic.
	* /You should only be concerned about passing this specific test. That is the only thing to think about right now. Stop trying to solve the rest of the challenge!/
* Rinse and repeat
	* Write another failing test but keep it simple!
	* Write some easy code to pass the tests.
	* Do this for a few simple tests until you feel that things are getting messy and would benefit from some more complicated logic.

**Move on to Step 3**

## Step 3 - PLANNING PHASE 2

#### This phase can be iterative. You can plan then go back to testing and get that passing then go back to planning. Even running the same test multiple times to get your code working.

* Here is where you will want to start demystifying the black box.
* Start thinking about how you can solve this problem and get to the final acceptance criteria.
* Think about the problem and try to demystify it by thinking about things in terms of how you would do it in real life on paper.
	* Let’s use the Scrabble Letter Kata (Counting up a scrabble score given the letters used) as an example.
		* If given the tiles that were played and asked for the score how would you do that?
			* My first thought would be that I would need to look at each letter individually (in Ruby terms that sounds like I need to have the given string broken up so that I can look at them individually. `array`?, `.chars`?, `.each`?).
			* Next I would need to compare that letter against the score card (hmm sounds like I need a score card…. I would imagine that as some kind of `hash`. `{‘a’ => 1, 'b' => 2.....`)
			* I’ll need to record the score for each letter (`array`?`.push()`?)
			* Once I’ve gone through every letter I’ll have a list of scores that will need to get added up  (`return array.inject(:+)`?)
* Once you feel confident to start you can start to rework your code.
* Any methods you feel unsure about you could consider playing with them in IRB to check the behaviour is as you expect.

**Move on to step 4**

## Step 4 - REFACTORING CODE

* You already have your tests for some simple logic so you’ll know if you’ve been successful in refactoring the code when those tests are passing again.
* You don’t have to refactor all at once either.
* In terms of the Scrabble Letter Kata maybe you create a hash that just returns the scores for the letters that you used in your simple tests.
* Maybe then you write a test for a larger word.
* After you’ve put maybe 6 letters in your hash to solve the tests you have you could think about finishing off the score card to include the entire alphabet.
* At this point you can think about testing for edge cases
* You’ll have to look back to the acceptance criteria you originally created to see at what point you can consider yourself finished.

*That’s it! You’re finished!*
*That wasn’t so hard was it? ;)*
