# Lab Report 4

# Step 1 - Log into ieng6

![Image](logIn.png)

Keys pressed :  
- `ssh rsrikanth@ieng6.ucsd.edu <enter>` to log into ieng6. I wasn't prompted to enter my password because I have set up the SSH key with my computer.

# Step 2 - Clone your fork of the repository from your Github account 

![Image](clone.png)

Keys Pressed : 
- `rm -rf l<tab> <enter>` which tab completes the command to `rm -rf lab7/`. This deletes the `lab7` directory which is currently in my ieng6  account.    
- `<Command-C> git clone <Command-V> <enter>` to copy the ssh URL `git@github.com:Ridzz23/lab7.git` and clone my fork of the `lab7` repository.

# Step 3 - Run the tests, demonstrating that they fail
![Image](failedTests.png)

Keys Pressed : 
- `<up> <up> <up> <up> <up> <enter>` to compile all java files. The command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` was 5 up in the search history so I used up arrow to access it.    
- `<Command-C> <Command-V> <enter>` to copy the command and run `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`.

# Step 4 - Edit the code file to fix the failing test

![Image](vim.png)

Firstly, I typed `vim List<tab>.java <enter>` which tab completes to `vim ListExamples.java`. This allows me to enter the file `ListExamples.java` using the text editor `vim`.
To navigate to the line which needs to be fixed I press the following keys :
- `<down arrow>` 43 times
- `<right arrow>` 11 times   
Now that I have reached the point of error I have to edit it. I press the following keys to do so :
- `i` to enter insert mode
- `<right arrow>` to move to the next spot
- `<Backspace>` to delete the number 1
- `2` to add the number 2
- `<esc>` to exit insert mode and enter normal mode   
The change has been made. Now I need to save the changes and exit the text editor. I press `:wq<enter>` to save and exit.


# Step 5 - Run the tests, demonstrating that they now succeed

![Image](passedTests.png)

To re-run the tests I pressed the keys :
- `<up> <up> <up> <enter>` to run the command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` which was 3 commands up. This re-compiles all the java files.
- `<up> <up> <up> <enter>` to run the command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` which was 3 commands up. This re-runs `ListExamplesTests`.

# Step 6 - Commit and push the resulting change to your Github account

![Image](commit.png)

Keys Pressed : 
- `git add . <enter>` which prepares the current directory (`lab7/`) to be committed. 
- `git commit -m "Fixed the error" <enter>` which makes the commit with the message "Fixed errors".
- `git push <enter>` to push the commit to github. 


