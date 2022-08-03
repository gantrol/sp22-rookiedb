Your Tasks

For this assignment you will get acquainted with running RookieDB's command line interface and make a small change to one file to get things working properly.

# Task 1: Running the CLI

Most databases provide a command line interface (CLI) to send and view the results of queries. To run the CLI in IntelliJ navigate to the file:

```
src/main/java/edu/berkeley/cs186/database/cli/CommandLineInterface
```

It's okay if you don't understand most of the code here right now, we just want to run it. Locate the arrow next to the class declaration click on it to start the CLI.

![img](https://3248067225-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MFVQnrLlCBowpNWJo1E%2Fsync%2F5a4de4c7d0ddde02ad4bd05e3938198a93f3c469.png?generation=1598272179258074&alt=media)

Click the arrow (circled in red above) to run the CLI

This should open a new panel in IntelliJ resembling the following image:

![img](https://3248067225-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MFVQnrLlCBowpNWJo1E%2Fuploads%2Fgit-blob-39d89c33aadc2526e0a5d9ceeb91c8e4c8252106%2Fimage%20(10)%20(1)%20(1).png?alt=media)

Click on this panel and try typing in the following query and hitting enter:

```
SELECT * FROM Courses LIMIT 5;
```

You should get something similar to the following output:

![img](https://3248067225-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MFVQnrLlCBowpNWJo1E%2Fsync%2Fb720005287f6253bac3bf8df4fc9be45f1ae035a.png?generation=1598272178939307&alt=media)

Hmm, that doesn't look quite right! Follow the instructions in the next task to get the proper output. To exit the CLI just type in `exit` and hit enter.

# Task 2: Welcome to CS186!

Open up `src/main/java/edu/berkeley/cs186/database/databox/StringDataBox.java`. It's okay if you do not understand most of the code right now.

The `toString` method currently looks like:

1

​    @Override

2

​    public String toString() {

3

​        // TODO(proj0): replace the following line with `return s;`

4

​        return "FIX ME";

5

​    }



Copied!

Follow the instructions in the `TODO(proj0)` comment to fix the return statement.

Navigate to`src/test/java/edu/berkeley/cs186/database/databox/TestWelcome.java` and try running the test in the file, which should now be passing. Now you can run through Task 1 again to see what the proper output should be.

(If you see anything highlighted in red in the test file, its likely that JUnit wasn't automatically added to the classpath. If this is the case, find the first failed import and hover over the portion marked in red. This should bring up a tooltip with the option "Add JUnit to classpath". Select this option. Afterwards, no errors should appear in the file.)

# Task 3: Debugging Exercise

In this course, a majority of the projects are written in Java and involve modifying a large codebase. Knowing how to effectively utilize the IntelliJ debugger will be important in identifying errors with your code. Let's cover the basics of using the IntelliJ debugger!



As you follow along with the steps below, please submit your answers to this [Gradescope assignment](https://www.gradescope.com/courses/345707/assignments/1779425). You must complete this for full credit.

Let's start by navigating to src/java/test/.../index/TestBPlusNode.java.

### Breakpoints

Place a breakpoint as shown below. Breakpoints allow you to select locations in your code where you want the debugger to pause.

![img](https://3248067225-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MFVQnrLlCBowpNWJo1E%2Fuploads%2Fgit-blob-cefaeedac3f3d354e1e551f58190f622a2e5a9b8%2FScreen%20Shot%202022-01-17%20at%2011.41.55%20PM.png?alt=media)

### Running the debugger

Select the green arrow next to the function header for testFromBytes. In the dropdown menu, click debug. This will open a debugging console at the bottom. The code is currently paused at the line we placed a breakpoint on.

![img](https://3248067225-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MFVQnrLlCBowpNWJo1E%2Fuploads%2Fgit-blob-011bd2fe36bc500c293199d90e311fc7e919728f%2FScreen%20Shot%202022-01-17%20at%2011.39.45%20PM.png?alt=media)

### Inspecting variables

![img](https://3248067225-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MFVQnrLlCBowpNWJo1E%2Fuploads%2Fgit-blob-5005c51313e4c645a5920f74a21d3cfe74c049db%2FScreen%20Shot%202022-01-17%20at%2011.56.14%20PM%20copy.jpg?alt=media)

The debugger allows you to inspect relevant variables in the code



Question 1: What is the current size of 'leafKeys'?

### Step into

Click on the button shown below to step into the LeafNode constructor.

![img](https://3248067225-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MFVQnrLlCBowpNWJo1E%2Fuploads%2Fgit-blob-22816b4115593b7a5d39f94b7159e676dd6e5a21%2FScreen%20Shot%202022-01-18%20at%2012.00.53%20AM%20copy.jpg?alt=media)

### Step over

Click on the button shown below to step forward one line.

![img](https://3248067225-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MFVQnrLlCBowpNWJo1E%2Fuploads%2Fgit-blob-158acca96e636deb264f7fc10be4e94e8cb11edd%2FScreen%20Shot%202022-01-18%20at%2012.00.53%20AM%20copy%202.jpg?alt=media)



Question 2: What is the current size of 'rids'?

### Resume execution

This button allows you to resume execution of your program until it reaches another breakpoint. Don't worry if testFromBytes fails after resuming execution. You won't pass this test until project 2.

![img](https://3248067225-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MFVQnrLlCBowpNWJo1E%2Fuploads%2Fgit-blob-f5150b86001e689409a26af728c10efb44530456%2FScreen%20Shot%202022-01-18%20at%2012.00.53%20AM.png?alt=media)

# You're done!

Follow the instructions in the next section "Submitting the Assignment" to turn in your work.