---
layout: post
title: Powershell - Switching JVMs and reloading PATH in place
---

I work a lot with java code and java projects for the DAISY Consortium and, in the current states of the project, we sometime have various versions of java required for working on different projects, thus I sometime need to change the default java version loaded in my terminal for a specific project.

When working on linux or macos, i often rely on SDKMAN! for doing such things, but it does not currently work on Windows (as of the date of this post, but I really hope it will do some day).

And even if I sometimes dislike it, I need to work on windows as most of my work for AVH or DAISY are windows-based or windows-related software (desktop apps or word addins), so i found a quick solution that i can script or copy past easily.

#  The context

I currently have 3 JVM installed globally on my work computer for various projects :
- A java 8 JDK distributed by Zulu
- A java 17.0.18.8-hotspot JDK distributed by Eclipse Adoptium / Themurin
- A java 25.0.2.10-hotspot JDK distributed by Eclipse Adoptium / Themurin

To ease a bit the switch, I added 3 environment variables on my system :
- `JAVA_HOME_8` points to the java 8 installation directory (`%PROGRAMFILES%\Zulu\zulu-8`)
- `JAVA_HOME_17` points to the zulu installation directory (`%PROGRAMFILES%\Eclipse Adoptium\jdk-17.0.18.8-hotspot`)
- `JAVA_HOME_25` points to the zulu installation directory (`%PROGRAMFILES%\Eclipse Adoptium\jdk-25.0.2.10-hotspot`)

Java 8 is mostly used to build the DAISY Pipeline 2 project on which I work regularly, so it is my default configured installation with `JAVA_HOME` set to the same value as `JAVA_HOME_8` and with the value of `%JAVA_HOME_8%\bin` registered in the `PATH` environment variable.

(Note that I had to remove the other jdk\bin folder from the path after there installation to ensure the correct version of java was called)


# Switching JVMS and reload path

With all of that ready, whenever i need to enable a specific JDK in a new terminal for a project, like my JDK for java 17, i can do the following to update the `$env:JAVA_HOME` used by most of the tools (like maven) to find the JDK to use for compilation.

```powershell
$env:JAVA_HOME = $env:JAVA_HOME_17
```

Then I can update and reload the current terminal "PATH" to prioritize the correct jdk with this command 
```powershell
$env:Path = "$env:JAVA_HOME_17\bin;" + [System.Environment]::GetEnvironmentVariable("Path","Machine") + ";" + [System.Environment]::GetEnvironmentVariable("Path","User")
```
To explain this command a bit, the "terminal path" is reloaded from the global machine and user specific environment variable (kudos to [this SOF answer](https://stackoverflow.com/a/31845512/4550930)).
But as the executables are searched in this env variables in their order of appearance in the PATH, we "prepend" the PATH reloading with the jdk bin folder to prioritize.

And that's it : for maven, i'm "temporarily" in a java 17 environment, until I close it or I reload the terminal PATH and JAVA_HOME variables.

