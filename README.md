# osu_linux_setup
How to setup an osu build environment on linux

A lot of people like to develop on linux, and some people want to contribute to the development of the [new open source osu! engine](http://github.com/ppy/osu)

So for those people, here is a quick guide on how to get a development environment up and running on linux.

## Using the monodevelop IDE (Easier)

Requirements:
* monodevelop
* git

**Ensure the mono version that is packaged with your monodevelop install is reasonably up to date (>= mono 4.9)**

First clone the main directory, ensuring that all subdirectories are initialised too.
```
git clone --recursive https://github.com/ppy/osu
```

Open the osu.sln file, found in the root directoy of the repo, in monodevelop.
You can now compile and run the program from the monodevelop IDE.

Done!

## No IDE (for people who don't like IDEs)

Requirements:
* git
* mono >=4.9
* nuget >= 2.12

First clone the main directory, ensuring that all subdirectories are initialised too.
```
git clone --recursive https://github.com/ppy/osu
```

Restore the required nuget packages for this project using the osu.sln file in the root directory of the repository.
```
nuget restore osu/osu.sln
```

Compile the project using mono. Newver versions of mono will have replaced `xbuild` with the  `msbuild` command.
```
<xbuild|msbuild> osu/osu.sln
```

Run the output executable
```
mono osu/osu.Desktop/bin/Debug/osu\!.exe
```

Done!

## Troubleshooting

During development, custom nuget sources may be specifid leading to Nuget not being able to source these packages. To resolve this, specify the `Nuget.Config` file in the top level directory when calling `nuget restore`.
 ```
 nuget restore -configfile Nuget.config
 ```
