# BowlingGame
using C++

# Design Document
The bowling program is designed to keep track of a person bowling score and to tally up the score to be displayed a final score at the end of all the user input. This program only supports a single person bowling at a time

# Data Structures and functions:
Within the program, there are two classes, a bowling class, and a frame class. The frame class is a data holder kind of object. For the private functions and variables, there is an array that is indexed at 21, being the max amount of throws a person can bowl in a single game and a frame counter that is designed to keep track of the current frame that the user is on. There are two booleans functions that return a true or false if a person got a strike or a spare. There are three more private functions where returns an integer from the score depending if the user got a strike or spare. There are four public functions, one of them being the constructor. The constructor just initializes the private two variables to be zero. The getRoll(int) returns the pins that were knocked down for a certain frame. The roll(int pins) is a setter function for setting the pins that were knocked down for that throw. The score() function calculates the score after each frame is played. The roll count is the index for the array rolls[]. The function uses a for loop to iterate through all 10 frames. The loop uses isStrike() and isSpare() functions to calculate the users score if the roll is a strike or a spare. The strikeBonus() function adds 10 points plus the next two rolls to the score and the spareBonus() function will add 10 points plus the next roll to the score. If the user does not get a strike or a spare, the score() function uses the sumOfPins() function to add the two rolls together to calculate the score.
The bowling class is a wrapper like class the uses the frames class. The bowling has the frame object and the bowlers name. The bowling class is the main driver in the program. This function, StartBowling(), is called in the main.cpp and once started, this will loop asking the user to input the data and displaying the score of that frame on the console after each frame has ended. The StartBowling() has for loop that runs for the first nine frames and after that for loop, there a section of code that enters 10th frame. The 10th frame is special because you have 3 throws if a user gets a strike or spare. At the end of each frame, there is a DisplayBowlingScore() function called the frames scoring calculation function and display the frame is an organized format on the console.

 
# User Document:
Bowling score is a console base program that keeps track of the a single person bowling score and displaying their final result at the end and having the program exits and quits. The source code is located at /export/home/cs330/cs330112/Project1/lib. For a user that wants to compile from the source code, they can run the Makefile by typing
make all
Or they can compile by typing:
 g++ main.cpp -o bowl_program Frame.cpp Bowling.cpp

The bowling program does not take in any command line parameters and runs by typing
./score_bowling

The program runs like and the following test data is some of what was tested, it is only here to give some example that the code can run and compile correctly.
Script started on February 26, 2018 01:36:22 AM CST

> pwd
/export/home/cs330/cs330112/Project1/lib
> ls
Bowling.cpp  Bowling.h    Frame.cpp    Frame.h      main.cpp     Makefile     testing.txt
> make
g++ main.cpp Bowling.cpp Frame.cpp -o score_bowling
> ls
Bowling.cpp    Bowling.h      Frame.cpp      Frame.h        main.cpp       Makefile       score_bowling  testing.txt
> ./score_bowling
Please enter players name:ben
__________________________________
Frame:1
-------> Enter roll 1: 5
Frame:1
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:10

__________________________________
Frame:2
-------> Enter roll 1: 5
Frame:2
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:25

__________________________________
Frame:3
-------> Enter roll 1: 5
Frame:3
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:40

__________________________________
Frame:4
-------> Enter roll 1: 5
Frame:4
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:55

__________________________________
Frame:5
-------> Enter roll 1: 5
Frame:5
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:70

__________________________________
Frame:6
-------> Enter roll 1: 5
Frame:6
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:85

__________________________________
Frame:7
-------> Enter roll 1: 5
Frame:7
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:100

__________________________________
Frame:8
-------> Enter roll 1: 5
Frame:8
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:115

__________________________________
Frame:9
-------> Enter roll 1: 5
Frame:9
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:130

__________________________________
Frame:10
Enter roll 1: 5

Enter roll 2: 5
Spare
Frame:10
Enter roll 3: 5
__________________________________
Frame score:150

__________________________________
> ./score_bowling
Please enter players name:benj
__________________________________
Frame:1
-------> Enter roll 1: -99
Invalid number of pins knocked down.
Valid numbers are between 0 to 10.
Please try again.
Frame:1
-------> Enter roll 1: 99
Invalid number of pins knocked down.
Valid numbers are between 0 to 10.
Please try again.
Frame:1
-------> Enter roll 1: d
Invalid input; please re-enter.
-------> Enter roll 1: d
Invalid input; please re-enter.
-------> Enter roll 1: f
Invalid input; please re-enter.
-------> Enter roll 1: s
Invalid input; please re-enter.
-------> Enter roll 1:
s
Invalid input; please re-enter.
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:10

__________________________________
Frame:2
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:30

__________________________________
Frame:3
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:60

__________________________________
Frame:4
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:90

__________________________________
Frame:5
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:120

__________________________________
Frame:6
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:150

__________________________________
Frame:7
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:180

__________________________________
Frame:8
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:210

__________________________________
Frame:9
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:240

__________________________________
Frame:10
Enter roll 1: 10
Strike.
Enter roll 2: 10
Strike.
Frame:10
Enter roll 3: 10
Strike.
__________________________________
Frame score:300

__________________________________
> ./score_bowling
Please enter players name:10
__________________________________
Frame:1
-------> Enter roll 1: 5
Frame:1
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:10

__________________________________
Frame:2
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:30

__________________________________
Frame:3
-------> Enter roll 1: 5
Frame:3
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:50

__________________________________
Frame:4
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:70

__________________________________
Frame:5
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:90

__________________________________
Frame:6
-------> Enter roll 1: 5
Frame:6
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:115

__________________________________
Frame:7
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:135

__________________________________
Frame:8
-------> Enter roll 1: 5
Frame:8
-------> Enter roll 2: 5
Spare
__________________________________
Frame score:155

__________________________________
Frame:9
-------> Enter roll 1: 10
Strike
__________________________________
Frame score:175

__________________________________
Frame:10
Enter roll 1: 5

Enter roll 2: 5
Spare
Frame:10
Enter roll 3: 10
Strike.
__________________________________
Frame score:205

__________________________________
> ./score_bowling
Please enter players name:benj
__________________________________
Frame:1
-------> Enter roll 1: 5
Frame:1
-------> Enter roll 2: 1
__________________________________
Frame score:6

__________________________________
Frame:2
-------> Enter roll 1: 3
Frame:2
-------> Enter roll 2: 7
Spare
__________________________________
Frame score:16

__________________________________
Frame:3
-------> Enter roll 1: 4
Frame:3
-------> Enter roll 2: 5
__________________________________
Frame score:29

__________________________________
Frame:4
-------> Enter roll 1: 6
Frame:4
-------> Enter roll 2: 0
__________________________________
Frame score:35

__________________________________
Frame:5
-------> Enter roll 1: 0
Frame:5
-------> Enter roll 2: 0
__________________________________
Frame score:35

__________________________________
Frame:6
-------> Enter roll 1: 5
Frame:6
-------> Enter roll 2: 7
Invalid number of pins knocked down. Valid numbers are between 0 to 5. Please try again.
Frame:6
-------> Enter roll 2: 4
__________________________________
Frame score:44

__________________________________
Frame:7
-------> Enter roll 1: 0
Frame:7
-------> Enter roll 2: 7
__________________________________
Frame score:51

__________________________________
Frame:8
-------> Enter roll 1: 6
Frame:8
-------> Enter roll 2: 0
__________________________________
Frame score:57

__________________________________
Frame:9
-------> Enter roll 1: 6
Frame:9
-------> Enter roll 2: 2
__________________________________
Frame score:65

__________________________________
Frame:10
Enter roll 1: 8

Enter roll 2: 1
__________________________________
Frame score:74

__________________________________
> exit

script done on February 26, 2018 01:38:23 AM CST


