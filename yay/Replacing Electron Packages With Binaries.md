## Introduction

Sometimes AUR helpers like `yay` or `paru` will install non-binary electron versions alongside packages. This becomes an issue when those electron versions become outdated as well as when they need to be updated since downloading and compiling electron versions is very resource intensive.


### Step 1.

Look for the electron packages installed on your system

`sudo pacman -Qs electron`

### Step 2.

Remove any debug packages. 

Example:

`sudo pacman -Runs electron<version>-debug`


### Step 3.

Use an AUR helper like `yay` to install `-bin` versions of the electron packages you found with `pacman -Qs electron`. Ensure you allow these new packages to replace the old ones.

Example:

`yay -S electron31-bin electron32-bin electron33-bin electron34-bin`

