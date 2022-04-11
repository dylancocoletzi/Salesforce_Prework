# Pre-work - *SUPER MARIO SAYS*

**SUPER MARIO SAYS** is a Character & Sound Memory game to apply for CodePath's SITE Program. 

Submitted by: **Dylan Cocoletzi**

Time spent: **36** hours spent in total

Link to project: https://glitch.com/edit/#!/sunset-sweet-nape?path=README.md%3A1%3A0

Please open preview in a new window to get the full game experience

## Required Functionality

The following **required** functionality is complete:

* [x] Game interface has a heading (h1 tag), a line of body text (p tag), and four buttons that match the demo app
* [x] "Start" button toggles between "Start" and "Stop" when clicked. 
* [x] Game buttons each light up and play a sound when clicked. 
* [x] Computer plays back sequence of clues including sound and visual cue for each button
* [x] Play progresses to the next turn (the user gets the next step in the pattern) after a correct guess. 
* [x] User wins the game after guessing a complete pattern
* [x] User loses the game after an incorrect guess

The following **optional** features are implemented:

* [x] Any HTML page elements (including game buttons) has been styled differently than in the tutorial
* [x] Buttons use a pitch (frequency) other than the ones in the tutorial
* [x] More than 4 functional game buttons
* [x] Playback speeds up on each turn
* [x] Computer picks a different pattern each time the game is played
* [x] Player only loses after 3 mistakes (instead of on the first mistake)
* [x] Game button appearance change goes beyond color (e.g. add an image)
* [x] Game button sound is more complex than a single tone (e.g. an audio file, a chord, a sequence of multiple tones)
* [ ] User has a limited amount of time to enter their guess on each turn

The following **additional** features are implemented:

- [x] When the user loses the game, a losing sound plays
- [x] When the user wins the game, a winning sound plays
- [x] An accurate "lives left" display to inform the user of their lives
- [x] Changed the font to a custom Mario Game font to set a Mario Game theme 
- [x] Added a Mario Game background to set a Mario Game theme 

## Video Walkthrough (GIF)

Start and Stop button in action:

![Screen Recording 2022-03-26 at 5 27 01 PM](https://user-images.githubusercontent.com/86747062/160263847-231cc29a-640c-4ca5-a58b-256d122be375.gif)

Give user two strikes in action:

![Screen Recording 2022-03-26 at 5 29 47 PM](https://user-images.githubusercontent.com/86747062/160263953-eed17ded-4dd8-41ea-93bb-500e24d069fd.gif)

Demonstration of user winning the game:

![First Part](https://user-images.githubusercontent.com/86747062/160266100-d6183558-9be5-48bd-bebe-fccbb5e8510e.gif)


![Second Part](https://user-images.githubusercontent.com/86747062/160266273-c06f0d3f-6c0e-4a16-82b4-0bb0f3fc3e9b.gif)

## Reflection Questions
1. If you used any outside resources to help complete your submission (websites, books, people, etc) list them here. 
https://www.w3schools.com/js/js_random.asp, https://stackoverflow.com/questions/2856059/passing-an-array-as-a-function-parameter-in-javascript, https://www.w3schools.com/cssref/pr_background-image.asp, https://www.youtube.com/watch?v=Hwq_Mr12bcI, https://www.w3schools.com/css/css_border_color.asp, https://www.w3schools.com/js/js_output.asp, https://www.w3schools.com/jsref/met_audio_play.asp, https://www.w3schools.com/howto/howto_css_button_group.asp

2. What was a challenge you encountered in creating this submission (be specific)? How did you overcome it? (recommended 200 - 400 words) 

One challenge I encountered in creating this submission was implementing the feature where I allowed the user to make two mistakes before losing the game. I implemented this feature by creating a variable “lives” that contained the value two and one life would be deducted for every mistake. It would first check if the variable “lives” equaled zero and if that was true, it would call the function loseGame(). All of this was modified into the function guess(btn). I thought this new feature worked, but I didn’t take inconsideration the implementation of speeding up the clue playback on each turn. I specifically chose to decrease the variable clueHoldTime by twenty inside the for loop because this will allow the user nine turns before the speed becomes too fast to be visible and audible. Before, the maximum possible number of turns was nine, but now since the user can make two mistakes before losing, they can repeat two turns which changes the new maximum possible number of turns to eleven. This means if the user makes two mistakes and it passes turn “nine”, they wouldn’t be able to see and hear the pattern to repeat. To overcome this challenge, I knew I just had to add back the time taken away to the variable clueHoldTime. I created a variable errorSequence that kept track if the user guessed incorrectly. It was initialized to false because the user can’t guess wrong before the game starts. The variable errorSequence would turn true if the user guessed incorrectly and the variable “lives” doesn’t equal zero. This was implemented into the function guess(btn) and then I modified the function playClueSequence(). I created a conditional statement that would check if variable errorSequence is true. If it is true, it will add twenty back to the variable clueHoldTime and then proceed to play the pattern. After the for loop, the variable errorSequence is set to false so it doesn’t add more time back to clueHoldTime. I tested my program but after the ninth turn, the speed was still too fast to see or hear. After looking over the function playClueSequence(), I saw that I decreased the clueHoldTime inside the for loop, so the time decreased is the variable “progress” times twenty. So I replaced the body of the conditional statement to add the variable “progress” times twenty instead of adding twenty.

3. What questions about web development do you have after completing your submission? (recommended 100 - 300 words) 

After completing my submission, one question about web development that I have is how does HTML and JavaScript correlate with each other to create web pages and programs because it seems like there is no flow to the structure of the program. In programming languages I’m used to, like Python and C++, there is a flow to the structure that starts at the first line of a file and ends at the last line of it. I thought there has to be one specific main function that contains the primary structure of the program and in that main function it calls other functions that are needed in order for the program to run. At first, I thought the main function of my submission was the function startGame() because that function initializes the game, but after reviewing the code I was confused on where the function guess(btn) played a role since it is not called inside the startGame() function. Then I started to think that maybe the main function was inside the HTML file because in order to use functions like startGame() and guess(btn), the user must click on the button. My hypothesis is that the main file is the HTML file and the header file that contains the declaration and definition of the functions is the JavaScript file. Then I started to realize that the HTML file only has the elements of the web page and what function those elements are supposed to call but contains no structure of the program. Since I can’t identify the main structure of the program, I want to know if maybe those two files make up the structure of the program or do the tags in the HTML file connect all aspects of the files needed?

4. If you had a few more hours to work on this project, what would you spend them doing (for example: refactoring certain functions, adding additional features, etc). Be specific. (recommended 100 - 300 words) 

If I had a few more hours to work on this project, I would spend it on adding the corresponding sounds to each character on the button to contribute to the theme of Super Mario. I tried for several hours to add a unique sound to each character, but I encountered a couple problems. The first problem was that when the clueHoldTime was very small, the sound would continue to play. The second problem was that if the sequence repeated a button twice, the second time the button was clicked, the sound wouldn’t play. I believe I encountered these two problems because I didn’t constrain the sound to play to the corresponding clueHoldTime. To fix these two problems, I think what I would have to do is implement two new functions, playSound(btn) and stopSound(btn). I would make a dictionary similar to the freqMap one and the key would be the button number and its value would be the id of the audio tag. From there the playSound(btn) would play the sound corresponding to the button number and this function would be inside both playTone() and startTone() which would replace the lines of code that play the frequency sound. stopSound(btn) would stop the sound corresponding to the button number and this function would be inside the stopTone() to replace the line of code that stops the frequency sound.



## Interview Recording URL Link

[My 5-minute Interview Recording] https://www.loom.com/share/4dffbb645da448c0a83a046199956a55


## License

    Copyright [Dylan Cocoletzi]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
