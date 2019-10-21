# spsox
Simple Bash script for creating spectrograms from flac files. 

I found no script or program that would produce spectrograms how I liked so I made this script for people like me who require
a simple solution.

# Requires

[SoX](http://sox.sourceforge.net/)

[Bash](https://www.gnu.org/software/bash/) 

You should already have bash if you use GNU/Linux. 

[Git](https://git-scm.com/download/linux) 

Only if you want to clone the repository.
# Installation

Open a terminal and type or paste the following.
`git clone https://github.com/EwolBash/spsox.git`

Next we move into the directory

`cd spsox`

We make the script executable so we can run it.

`chmod +x spsox`

Now we move it to the local bin directory so you can call it from wherever you need to.

`sudo cp spsox /usr/local/bin/`

That's it.

# Usage

There's two main options.

`spsox`

and

`spsox -r`

Simply typing `spsox` within the directory containing the flac files will run it on all the flac files contained in the directory.
It will then create a directory and move the spectrograms into a folder named 'specs'. It will create a full spectrogram of each file and a 2 second zoomed in spectrogram.

Using `spsox -r` requires you to specify a directory after which it will run on all files recursively. It will look for flac files in every folder and sub folder within the directory you specify. This is useful when you want to create spectrograms of multiple albums. Use with care.

# Issues

Any problems feel free to open an issue/ticket.

I'm not sure how this will behave on windows using WSL. If it is not working I have a legacy version named oldspsox. If spsox is working fine you can ignore oldspsox as it's not as useful and only works within the current directory.
