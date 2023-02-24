# Summary

In order to follow these steps and complete them, this guide will assume you are on a new terminal, with no relevent command history.

For speedrunning purposes, you will want to copy paste these commands in groups, thereby saving you the time between commands. There is also a method to change the file from the command line, but that will not be included in this guide.

## 1. Setup: Delete any existing forks of the repository you have on your account

Ignore this step if its the first time you've cloned this repository.

Since you've already made changes to the repository from the last step, you will need to delete it and start over. Go to `Settings` and scroll all the way down. At the bottom, it should look like this:

![Screenshot_20230223_061058](https://user-images.githubusercontent.com/110417453/221074893-ec1b40a1-30da-4634-94a0-2e58e229a83d.png)

Press `Delete this repository` and confirm by typing `<Your username>/lab7`.

![Screenshot_20230223_061204](https://user-images.githubusercontent.com/110417453/221075006-c84bb97d-8aee-48f5-8b47-b920df8e576b.png)

Now press `I understand the consequences, delete this repository` and if it prompts you for your password, input it. 

Now you'll need to remove the instance of the repository from your ieng6 account. Type `cd` to return to the home directory, then type `rm -rf lab7/` to remove the `lab7/` directory and all files inside it.

![Screenshot_20230223_062603](https://user-images.githubusercontent.com/110417453/221077101-15140812-3f11-4193-bef3-92d56b386bf4.png)

Now you're all set to start over again.

## 2. Setup: Fork the repository

To fork the repository, go to: https://github.com/ucsd-cse15l-w23/lab7 and press `Fork` at the top right.

![Screenshot_20230223_061410](https://user-images.githubusercontent.com/110417453/221075276-877d8731-636a-4d2a-962b-a6ba2d07b238.png)

It will take you to this screen, where you just need to press `Create fork` at the bottom.

![Screenshot_20230223_061443](https://user-images.githubusercontent.com/110417453/221075405-75a4a734-1e74-4b0b-b773-f3ab4629cbb5.png)

Now your fork is made and your can continue.

## 3. The real deal Start the timer!

On your phone or another device, start a stopwatch to see how quickly you can complete these steps. If you are worried about being extremely fast, I recommend using your phone or another device, so you can start typing as soon as you start the stopwatch.

## 4. Log into ieng6

In a terminal, run the command `ssh cs15lwi23___@ieng6.ucsd.edu`, where the `___` is replaced with your specific account. In my case, it is `atl`.

![Screenshot_20230223_053417](https://user-images.githubusercontent.com/110417453/221070604-069da15d-1f7a-4783-8f7b-f593bf6096c3.png)
![Screenshot_20230223_053427](https://user-images.githubusercontent.com/110417453/221070613-11dda22d-a192-471f-bdd7-84918a24ef39.png)

Here, you can see me enter this and it will log me into `ieng6`. You can avoid putting in your password by generating an ssh key, which allows you to log in without password.

## 5. Clone your fork of the repository from your Github account

Now you need to clone your repository. On github, use the ssh link to do `git clone`.

The link can be found here:

![Screenshot_20230223_053820](https://user-images.githubusercontent.com/110417453/221071399-688d0257-19fe-4456-a65c-4d269bae3dc8.png)

For my repository, I would use the command `git clone git@github.com:ConnortheFan/lab7.git`. 

![Screenshot_20230223_054133](https://user-images.githubusercontent.com/110417453/221071437-4b504dd8-1074-4e04-baa5-74b871f25e34.png)

Since I have already used my ssh code to connect to github, this works smoothly and you won't need any additional steps to commit and push your changes to the repository.

Now, change your directory to the newly cloned repository with: `cd lab7/` to start working. If you have no other files that start with the letter `l`, you can type `cd l`, then press `<Tab>` to autocomplete.

![Screenshot_20230223_054147](https://user-images.githubusercontent.com/110417453/221071448-67820550-a3de-41ab-b3d0-0b03ecccdec5.png)

If you type in `ls`, it should display these files to demonstrate you've done these steps correctly.

## 6. Run the tests, demonstrating that they fail

Now you want to enter these two commands:

```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
```

If you copy and paste these 2 lines, your program can run them both in order, which saves you the trouble of typing it out.

![Screenshot_20230223_054517](https://user-images.githubusercontent.com/110417453/221071743-47ca5f84-e3b3-424a-a9d3-9fdac3cdca89.png)

These commands will run the JUnit tests from the ListExamplesTests.java file, using the JUnit packages from `lib/`.

Here, it should display that your tests have failed.

## 7. Edit the code file to fix the failing test

Now we need to edit the code to make the tests pass. In order to do this, you should open the `ListExamples.java` file by running `nano ListExamples.java`. 

If you are typing this command, simply type `nano L`, then hit `<Tab>`. This will autocomplete to `nano ListExamples`. Now press `<.><j>` so it looks like `nano LIstExamples.j` and hit `<Tab>` to autocomplete to `nano ListExamples.java`

![Screenshot_20230223_054806](https://user-images.githubusercontent.com/110417453/221072064-359304ea-4087-4453-8821-773b029cba36.png)

A screen like this will take over the terminal which displays the contents of `ListExamples.java`. Use the arrow keys to navigate to the bottom. The bug in our code is that this while loop is incrementing index1 instead of index2. Use the arrow keys to hover over that part and change it.

![Screenshot_20230223_054953](https://user-images.githubusercontent.com/110417453/221072307-b7e002be-b948-4781-a1c4-c9dc55132bdf.png)
![Screenshot_20230223_055000](https://user-images.githubusercontent.com/110417453/221072314-fbb1db91-f9a8-479f-844f-793bf872ca67.png)

Once you've made the change, you want to save it. Press `<Ctrl-O>` and then press `<Enter>`. This will save your change. Now press `<Ctrl-X>` to exit the file editor.

## 8. Run the tests, demonstrating that they now succeed

Now that the file has been fixed, we want to run the same commands as in step #6. We can either copy and paste it again or use our arrow keys. If you press `<Up><Up><Up>`, it will go to the 3rd most recent command, which is `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`. This will compile the files you just edited. Hit `<Enter>` to run it

Now hit `<Up><Up><Up>` again for the 3rd most recent command again, which is now `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`. Press `<Enter>` to run the tests.

![Screenshot_20230223_055318](https://user-images.githubusercontent.com/110417453/221072853-8c484126-817f-42c6-b0f6-15665a222dcd.png)
  
If done correctly, your tests should now all pass.

## 9. Commit and push the resulting change to your Github account (you can pick any commit message!)

Now that our change has been made, we want to send that change to Github.
    
Use the command `git add ListExamples.java` to stage this file. Now do `git commit -m "<Message>"`, where you place your own message instead of `<Message>`. This will send the change your staged and save it. 
  
![Screenshot_20230223_055803](https://user-images.githubusercontent.com/110417453/221073383-7a489bd3-8674-4753-b7d3-a5a6e6d08283.png)
  
Finally, do `git push`, which will send all changes you've committed to Github, where the change will show up on the files.

![Screenshot_20230223_055810](https://user-images.githubusercontent.com/110417453/221073413-6397856a-58ca-45b3-8e0d-82c28d38b4cc.png)

To show that these changes have gone through, go to your Github repository, and see if your message shows up next to `ListExamples.java`.

![Screenshot_20230223_060359](https://user-images.githubusercontent.com/110417453/221074062-9812e3d6-9ed3-4f0c-bbac-37137db97558.png)

Now you've finished, and can stop your timer.
