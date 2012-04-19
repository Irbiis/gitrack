# gitrack
by Derek Ashley Thomas and anyone who wants to contribute

gitrack is a way to keep track of your git repositories and compare them
to the origin. If you are like me, you work on many projects and want a
quick one-line command to check their state, fetch, merge, or even push
all at once, now you can! Now you can know right away how many commits
ahead/behind your local copy is and handle it without going too far away
from your origin.

## Available Options

There are several options currently available, and hopefully it can grow
from here.

The help info is easily available with the `--help` flag:

    gitrack Usage: gitrack [--logs-dir {directory}] [--logs-file {file-name}]
                           [-c] [-iflLmpqv] [-s {directory}]
    EXPLANATION
        gitrack is a program designed to log and maintain several
        git repositories collectively. This way you can push, fetch, and
        merge from multiple repositories in a row for several unrelated
        projects. It also makes it possible to share/sync multiple repos
        accross multiple computers quickly. A single log file is created
        for this: '\$LOGS_DIR/gitrack_record' [by default].
  
        Make sure that LOGS_DIR is an environment variable set your shell
        startup file before running. You could also specify this directory
        by using the '--logs-dir' option.
  
    OPTIONS
        -c   --collect      collect [run in the parent directory]
        -i   --info         print detailed information
        -f   --fetch        fetch (clones the repository if not already)
        -l   --list         list all of the tracked repositories
        -L   --LICENSE      print license information
        -m   --merge        merge (clones the repository if not already)
        -p   --push         push
        -q   --quiet        quiet mode [set by default]
        -s   --select       select only a single given directory
        -v   --verbose      verbose mode
  
        --logs-dir={dir}    override LOGS_DIR environment variable
        --logs-file={file}  specify the log file to read from [default: gitrack_record]
  
    ENVIRONMENT
        LOGS_DIR   A directory that holds log information. Can be an available environment variable
        ~/.colors  Can be a file that holds shell variables with color names. If available, it is sourced.

## Example 

Consider the following directory tree


    /some/path/dev              
    ├── major-project [git-repo]
    ├── project1      [git-repo]
    └── project2      

First, collect all of our git repositories into gitrack:

    $ cd /some/path/dev
    $ gitrack --colect
    gitrack: collect
    new > major-project
    new > project1

We can then check on our repositories from anywhere

    $ cd /somewhere/else
    $ gitrack
    ================= 
    major-project:              
      - branch: master
        * ahead:  ↑ 14
      - status:       
        * staged:   0 
        * modified: 1 
        * others:   1 
    ================= 
    projcet1:              
      - branch: master
      - status:       
        * staged:   3 
        * modified: 2 
        * others:   0 

There's a lot more you can do, too. And, if there's something you can't
do, but want it to do? Have a go and fork the heck out of it!

* * * * * * * * * * * * * * * * * * * * * * * * * * * * * * 

# License
**gitrack**: keep track of multiple git repositories and projects with one command!
Copyright (C) 2012 **Derek Ashley Thomas**

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
