# idea-gradle-template

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

After you have a **good** name, you can begin with the following:

1. Open IntelliJ IDEA.
1. Click `Create New Project`.
1. In the left panel, select `User-defined`.
1. In the right panel, select `ELE115`.
1. Click `Next`.
1. In file `settings.gradle`, replace `<your-project-name>` with your project name.
1. In file `build.gradle`, replace ALL occurancess of `<your_project_name>` with your project name,
but **using underscore instead of hyphen** to separate words.
1. In file `build.gradle`, replace ALL occurancess of `<your_netid>` with your netid.
No capital characters.
1. In `Project` panel, right-click on the folder `src/main/java`, click `New`/`Java Class`.
1. In the `New Java Class` dialog, fill in `Name` field by `com.github.ele115.<your_netid>.<your_project_name>.Main`.
1. Start writing your program now!
