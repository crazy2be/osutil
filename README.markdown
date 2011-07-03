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

Full function reference is available at http://gopkgdoc.appspot.com/pkg/github.com/crazy2be/osutil.