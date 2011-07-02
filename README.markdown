OS Utility Package
==================

Utility functions for functionality you would expect to find in the os package, such as running programs and testing if files exist. Most of the program running functions are deprecaiated now that the exec package has been updated in the latest weekly.

Getting Started
---------------

Install:

	goinstall github.com/crazy2be/osutil

Import:

	import "github.com/crazy2be/osutil"

Use:

	osutil.WaitRun("cp", []string{"-r", "foo", "bar"})

Functions
---------

### func FileExists(name string) bool
Checks if a file exists, returns true if the file exists and can be opened, false otherwise. If the file exists but cannot be opened, it still returns false.
NOTE: Assumes that any error opening the file for reading means that the file does not exist. This is not always true, but is probably the best behaviour anyway. There is rarely a usage case where you want to check if a file exists, but not if you can open it.

### func Run(command string, args []string) (proc *exec.Cmd, err os.Error)
Simple way to run most programs. Searches for the program in PATH, and runs the first found program. Args need not contain the program name as the zeroth argument, it is prepended automatically.

### func RunWithEnv(command string, args []string, env []string) (proc *exec.Cmd, err os.Error)
More advanced, runs a program with a custom enviroment. Note that the normal enviroment is also passed here, as that is what is typically desired. Enviroment is a slice of strings, with each string usually having the form "NAME=VALUE". If you pass an enviroment string of the form NAME=VALUE that has the same name as an existing enviroment string, your value overwrites the value of the other variable.

### func RunWithEnvAndWd(command string, args []string, env []string, wd string) (proc *exec.Cmd, err os.Error)

### func WaitRun(command string, args []string) (proc *exec.Cmd, err os.Error)
Runs a command using Run(), but waits for it to complete before returning.
