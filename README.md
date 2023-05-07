Download Link: https://assignmentchef.com/product/solved-laboratory-exercise-6-manipulating-sounds
<br>
<p class="ui header product-top-header" title="Laboratory Exercise 6: Manipulating Sounds Solution">OverviewThe objectives of this lab are: To review the for loop To review the index system for arrays To work with ranges To review functions with parameters and return valuesI. Changing VolumeOpen JES and start up a new program. Save your file with a suitable name such as <a href="http://lab6.py/" target="_blank" rel="nofollow noopener noreferrer">Lab6.py</a> or something similar. Add comments to the top that describe the file as a whole, such as:# Lab 6: Manipulating Sounds# Your Name and your partner’s name# Today’s DateThe following function allows us to increase or decrease the volume of a sound by any factor. Copy it into JES, add appropriate comments, and try it out:1. What do you think the duplicateSound function does? In JES, go to Help and then choose Sound Functions. Find duplicateSound, compare the description of this function with your guess, were you right? Do you think there is a similar function for images? Type your answers as a comment underneath the changeVolume function.2. In the changeVolume function, every sample value is multiplied by the same factor. There is nothing to stop us from changing the volume of different parts of the sound by different amounts. In particular, we will write a function that leaves the volume at the beginning of the sound unchanged, and then slowly reduces the volume over time. Your function should take two parameters: the sound, and the largest factor that the volume should be reduced by. Your function will return a new sound that fades out by the desired factor. For example, after thecommand:faded = fadeDown(sound, 8.0)the variable faded should contain a sound that is unchanged at the beginning, and quieter by a factor of 8.0 at the end.In order to accomplish this, you can create a variable, curFactor, that represents the amount that the current sample will be reduced by, and increase the value of that variable after each sample is processed. In other words, instead of the line:setSampleValue(s, val * factor) from the function above, your new function will have a line like the following:setSampleValue(s, val / curFactor)Note: When calling this function, the value used for the largest factor should be a floating point number. Otherwise, Python will use integer division, and your sound will not change.Design Questions: What should the initial value of curFactor be? (What amount can you divide a sample value by without changing the volume at all?) By how much should curFactor be increased after every sample? Keep in mind that this will depend on the total number of samples in the sound, which can be obtained using the getNumSamples function. Type your answers these questions in the form of a comment.2. Create a new function called fadeUp that slowly increases the volume of a sound by the desired amount. In other words, after this expression is executed:faded = fadeUp(sound, 8.0) the variable faded should contain a sound that is unchanged at the beginning, and louder by a factor of 8.0 at the end.3. Now write a function called fadeIn that makes the initial portion of a sound quieter by some factor, and then gradually increases the volume until it reaches the original level.II. Appending Sounds and using functions from a libraryIt is often useful to take two sounds and combine them into a single longer sound. This can be done easily by making use of the copy (source, target, start) function we reviewed in class. In order to reuse functions we have written before, without having to re-type them in our new programs, we can create a library of useful functions. For this lab, I am providing you with such a library that contains functions to manipulate sounds. The name of the file is <a href="http://soundutilities.py/" target="_blank" rel="nofollow noopener noreferrer">soundUtilities.py</a>. We aregoing to import and use the functions in that library, in particular the copy (source,target, start) function.Please download the file <a href="http://soundutilities.py/" target="_blank" rel="nofollow noopener noreferrer">soundUtilities.py</a> and save it in the same directory where you have saved your <a href="http://lab6.py/" target="_blank" rel="nofollow noopener noreferrer">Lab6.py</a> file. Run another instance of JES and open <a href="http://soundutilities.py/" target="_blank" rel="nofollow noopener noreferrer">soundUtilities.py</a>.You will see the instruction from media import * in the first line. Scroll down until you  find the copy function. Take a look at it so you know how it works and what kind of parameters it takes.The next step is to set the library path on the command area. To do that, write the following instruction in the command area:addLibPath()A directory chooser will open. Navigate to the directory where you have saved<a href="http://soundutilities.py/" target="_blank" rel="nofollow noopener noreferrer">soundUtilities.py</a> and click the Open button.Note: if you are using a Mac, you may get an error message when trying to use addLibPath(), if that is the case use setLibPath() instead.Now in the program area, on your <a href="http://lab6.py/" target="_blank" rel="nofollow noopener noreferrer">Lab6.py</a> file, you need to type the following line at the beginning of the file:from soundUtilities import *We are now ready to write the appendSound function. Use the following code skeleton to create function that combines two sounds end to end:def appendSound(sound1, sound2):

# Make an empty sound long enough to contain both source sounds.# Copy sound1 into the beginning of the new sound using copy.# Copy sound2 into the new sound right after the end of sound1 using copy.# Return the new sound.Test your appendSound function to make sure that it works as expected.III. Blending Two Sounds TogetherThe process of blending sounds together is very similar to the process of blending two pictures together. The following function that we wrote in lecture is similar to Program #110 (page 257)in the textbook, and blends two very specific sounds:We will write a more general function to blend two sounds, as we did with pictures. The following is a skeleton for the function to blend two sounds. It takes two sounds and an overlap amount as parameters. The overlap amount is the number of samples that you want the two sounds to overlap – note that we do not necessarily want to overlap half of the first sound with half of the second sound.# Blend two soundsdef blendSounds(sound1, sound2, overlapAmt):# Get the lengths (# of samples) in each sound

# Make an empty sound large enough to hold the new sound. The# resulting sound would be combining the two sounds minus the overlap# Copy first sound up to the overlap section

# Add the overlap section

# Copy the rest of sound2

# return the new soundSubmitting your lab workFor this week’s lab you must submit the following items: Your .py file with the functions you wrote todayMake sure you and your partner save all your functions in a file with a proper name (like <a href="http://lab6.py/" target="_blank" rel="nofollow noopener noreferrer">Lab6.py</a> forexample) and submit it via Drexel Learn at the end of today’s lab.

5/5 - (1 vote)