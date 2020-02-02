## 1: Naming is a hard problem

Before you start, you must choose a **good** name for your project.
Basic rules for getting a good name is as follow.
Use hyphen to separate words. Only non-cap letters or numbers allowed. Don't start with a number or hyphen.
Two or more contiguous hyphens is forbidden. No trailing hypens.

Some examples of good project names:
```
hello-robot
advanced-drone-controller
ele115-assignment-1
```

Some examples of bad project names:
```
untitled
myfirstproject
project123
```

**Note:** your project name shall not be in conflict with Java keywords or literals:
```
true      false     null
abstract  continue  for         new        switch
assert    default   goto        package    synchronized
boolean   do        if          private    this
break     double    implements  protected  throw
byte      else      import      public     throws
case      enum      instanceof  return     transient
catch     extends   int         short      try
char      final     interface   static     void
class     finally   long        strictfp   volatile
const     float     native      super      while
```

## 2: Use the project templete

Whenver you have a *good* name for your project, you can begin with the following:

1. Open IntelliJ IDEA.
1. Click `Create New Project`.
1. In the left panel, select `User-defined`.
1. In the right panel, select `ELE115`.
1. Click `Next`.
1. Type your project's **name**.
1. Click `Finish`.

**Note:** If you don't see `User-defined`, checkout
[Setup Guide 3.2: Download ELE115 project template](https://github.com/ELE115/docs/blob/master/setup.md#32-download-ele115-project-template).

You should now see the IntelliJ IDEA workspace fully unwinded for you.
But don't panic, and **don't touch anywhere** for now.
Follow the instructions.

**Note:** If you see `Invalid VCS root mapping` prompt, simply close it.

**Note:** If you see `Tips of the day` dialog, simply click `Close`.

**Note:** Please do **NOT** click `Import Gradle Project` for now.
If you did, quit IntelliJ IDEA, delete your project, and start over from the beginning.

## 3: Edit Gradle files

To the left there is `Project` panel, in which you can see a list of files:

* `.editorconfig`: Specifies your coding style - what is allowed and what is forbidden. *You don't need to touch it.*
* `.gitignore`: What files should belongs to your program and what should not. *You don't need to touch it.*
* `build.gradle`: This is the most important configuration file, denoting some key characteristics of your program: **You MUST modify this file**
  * Which language is your program written in?
  * Who wrote the program?
  * Where should the program start running?
  * Does the program depend on other programs? What are they? Where can I find them?
* `gradle.properties`: This file tweaks some auxiliary features in Gradle. *You don't need to touch it.*
* `gradlew`/`gradlew.bat`: These are auxiliary programs that reads `build.gradle` and compiles your program. *You don't need to touch it.*
  * `gradlew` is for Linux and Mac OS users. Do *NOT* remove this file, even if you are not using Linux or Mac OS.
  * `gradlew.bat` is for Windows users. Do *NOT* remove this file, even if you are not using Windows.
* `settings.gradle`: This file records your program's name. **You MUST modify this file**.
* `External Libraries`: This is *NOT* an actual file nor folder. IntelliJ IDEA will be listing all your dependencies here. *You don't need to touch it.*
* `Scratches and Consoles`: This is *NOT* an actual file nor folder. IntelliJ IDEA allows you to store unused files here. *You don't need to touch it.*

We need to manually modify some files before we can proceed.
So follow the instructions:

1. In file `settings.gradle`, replace `<your-project-name>` with your project name.
1. In file `build.gradle`, replace ALL occurancess of `<your_project_name>` with your project name,
but **using underscores instead of hyphens** to separate words.
1. In file `build.gradle`, replace ALL occurancess of `<your_netid>` with your netid.
No capital characters.

**Note:** Make sure to remove `<` and `>`. For example:
```gradle
mainClassName = 'com.github.ele115.b1f6c1c4.my_project.Main'
```

**Note:** If you see `Non-Project Files Protection` dialog, simply click `OK`.

*Please double check: your project name in `mainClassName` has* **underscores** *instead of hyphens.*

## 4: Import Gradle Project

So now all Gradle-related stuffs are ready.
At the bottom right corner of your workspace, there should be a box titled `IntelliJ IDEA found a Gradle build script`.
In the box, click the `Import Gradle Project`.

This process may take seconds to minutes to execute.
What is happening is that `gradlew`/`gradlew.bat` is being executed and `build.gradle` is parsed.
Gradle noticed that you are willing to use Tello controller libraries,
so it is actively downloading it for you.
The controller is, unfortunately, gigantic in its size: 800MiB in total!
No wonder why it takes so long to download.

Just sit and wait for the process to finish.

**Note:** If you accidentally clicked `Skip` or closed the small box or just can't find such box, don't worry!
There is a small magnifier icon at the top right corner of your workspace.
Click the magnifier, and type `Import Gradle Project`.
Hit enter and that it! Just wait for it to finish.

After several minutes (or a fraction of second if this is not the very first time),
you should notice two things:

* To the **right** of your entire workspace, there is a new panel `Gradle` popped up. **You need to make changes in it.**
* To the left, your `Project` panel has changed. Files are grouped together.
New files and folders appear:
  * `.gradle` folder: this is where Gradle put some temporary files. *You don't need to touch it.*
  * `.idea` folder: this is where IntelliJ IDEA put its files in. *You don't need to touch it.*
  * `build` folder (you may not see it now, but you will see it soon): this is where Gradle put its output files in. *You don't need to touch it.*
  * `gradle` folder: internal settings for Gradle are stored here. *You don't need to touch it.*
  * `src/main/java` folder: **Here is where you should put your program files in!**

We start with the `Gradle` panel.

1. Click on the triangle before your project (should be the only item) in the `Gradle` panel.
1. Find `<your-project-name>`/`Tasks`/`application`/`run`.
1. Right click on it, and choose `Create '<your-project-name> [run]'...`.
1. Don't change any thing in the popped up dialog, simply click `OK`.
1. It's advisable to minimize the `Gradle` panel, since you will never use it anymore.
Just click the minus sign at the top right corner of the panel to minimize it.

**Note:** Don't *double click* on the `run`. If you already did, then just ignore the error messages and move on.

## 5: Setup Git

**Note:** This step is optional if this project is **NOT** a course lab.
However, we do encourage everyone to use Git to manage their development process.

Please follow the [Guide on setting up Git](https://github.com/ELE115/docs/blob/master/git.md#how-to-setup-git-for-a-single-project).

It is **highly recommanded** that you [Create a commit](https://github.com/ELE115/docs/blob/master/git.md#how-to-setup-git-for-a-single-project)
**immediately after** you *Import Gradle Project*
and **right before** you add any single line of Java code.

## 6: Start programming and have fun

Congratulations!
All your configurations have completed, we can commence coding!

1. In `Project` panel, unfold `<your-project-name>`.
1. In `Project` panel, right-click on the folder `src/main/java`, click `New`/`Java Class`.
1. In the `New Java Class` dialog, fill in `Name` field by `com.github.ele115.<your_netid>.<your_project_name>.Main`.
Remember, `<your_project_name>` should use underscores instead of hyphens to separate words.

Start writing your program now!

Whenver you want to execute your program,
simply hit `Shift+F10`,
or click the little green triangle at the top right corner of your workspace.
IntelliJ IDEA will launch `gradlew`/`gradlew.bat`, which will do the following:

* Parse `build.gradle`, understand what's going on
* Download newly added dependencies for you (if you request more)
* Compile your program
* Execute your program from the specified entrance

At the bottom you can see the output of Gradle, middle of which is your program's output.
