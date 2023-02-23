# Summary

In order to follow these steps and complete them, this guide will assume you are on a new terminal, with no relevent command history.

For speedrunning purposes, you will want to copy paste these commands in groups, thereby saving you the time between commands. There is also a method to change the file from the command line, but that will not be included in this guide.

## 1. Setup: Delete any existing forks of the repository you have on your account



## 2. Setup: Fork the repository



## 3. The real deal Start the timer!



## 4. Log into ieng6

ssh cs15lwi23atl@ieng6.ucsd.edu


## 5. Clone your fork of the repository from your Github account

git clone git@github.com:ConnortheFan/lab7.git

cd lab7/

## 6. Run the tests, demonstrating that they fail

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests


## 7. Edit the code file to fix the failing test

nano ListExamples.java

> Change index1 into index2

<Ctrl-O> <Enter> <Ctrl-X>


## 8. Run the tests, demonstrating that they now succeed

javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java

java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests


## 9. Commit and push the resulting change to your Github account (you can pick any commit message!)

git add ListExamples.java

git commit -m 'l'

git push
