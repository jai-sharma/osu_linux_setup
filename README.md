# osu_linux_setup
How to setup an osu build environment on linux

A lot of people like to develop on linux, and some people want to contribute to the development of the [new open source osu! engine](http://github.com/ppy/osu)

So for those people, here is a quick guide on how to geta development environment up and running on linux.

## Using the monodevelop IDE (Easier)

Requirements:
*monodevelop
*git

First clone the main directory, ensuring that all subdirectories are initialised too.
```
git clone --recursive https://github.com/ppy/osu
```

Open the osu.sln file, found in the root directoy of the repo, in monodevelop

Done!

## NO IDE (for people who don't like IDEs)

Requirements:
*git
*mono >=4.0
*nuget

First clone the main directory, ensuring that all subdirectories are initialised too.
```
git clone --recursive https://github.com/ppy/osu
```

Restore the required nuget packages for this project using the osu.sln file in the root directory of the repository.
```
nuget restore osu/osu.sln
```

Compile the project using mono xbuild.
```
xbuild osu/osu.sln
```

Run the output executable
```
mono osu/osu.Desktop/bin/Debug/osu\!.exe
```

Done!
