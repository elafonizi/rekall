---
layout: docs
title: Rekall Overview
---

The Rekall Framework is a completely open collection of tools, implemented in
Python under the GNU General Public License, for the extraction of digital
artifacts from volatile memory (RAM) samples.  The extraction techniques are
performed completely independent of the system being investigated but offer
visibilty into the runtime state of the system. The framework is intended to
introduce people to the techniques and complexities associated with extracting
digital artifacts from volatile memory samples and provide a platform for
further work into this exciting area of research.

The Rekall distribution is available from
[the Rekall project official website](http://www.rekall-forensic.com/).

Rekall supports the analysis of the following 32 and 64 bit memory images:

* Microsoft Windows XP Service Pack 2 until Windows 10
* Linux Kernels 2.6.24 to 4.20.
* OSX 10.6-10.11.

Rekall also provides a complete memory sample acquisition capability for all
major operating systems (see the tools directory). Rekall supports live
analysis out of the box.

## Quick start

Rekall is available as a python package installable via the pip package
manager. We support running Rekall under a virtualenv environment (This
guarantees that the exact versions of all dependencies are met).

Simply type (for example on Linux):

```sh
$ virtualenv  /tmp/MyEnv
New python executable in /tmp/MyEnv/bin/python
Installing setuptools, pip...done.
$ source /tmp/MyEnv/bin/activate
$ pip install rekall
```

To have all the dependencies installed. You still need to have python and pip
installed first.

To be able to run the ipython notebook, you will need to install the rekall-gui
package:

```sh
$ pip install rekall-gui
```

For windows, Rekall is also available as a self contained installer
package. Please check the download page for the most appropriate installer to
use.

## Development version

For development it is easier to install rekall inside a virtual env. Virtual Env
is a way for containing and running multiple versions of python packages at the
same time, without interfering with the host system.

```sh
# You might need to install virtualenv:
$ sudo apt-get install python-virtualenv

# This will build a new empty python environment.
$ virtualenv /tmp/Test

# Now we switch to the environment - all python code runs from here.
$ source /tmp/Test/bin/activate

# For development run the devel version
$ git clone https://github.com/google/rekall.git
$ cd rekall
$ python setup.py develop
```

When done you can just remove the `/tmp/Test` directory.

On Windows systems, the installtion process is covered in the blob post [Installing Rekall on Windows](http://rekall-forensic.blogspot.ch/2015/09/installing-rekall-on-windows.html).

## Mailing Lists

Mailing lists to support the users and developers of Rekall
can be found at the following address:

    rekall-discuss@googlegroups.com

## Licensing and Copyright

Copyright (C) 2007-2011 Volatile Systems

Copyright 2013-2016 Google Inc. All Rights Reserved.

All Rights Reserved

This program is free software; you can redistribute it and/or
modify it under the terms of the GNU General Public License
as published by the Free Software Foundation; either version 2
of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA
02111-1307, USA.


## Bugs and Support

There is no support provided with Rekall. There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR
PURPOSE.

If you think you've found a bug, please report it at
 [the Rekall issue tracker](https://github.com/google/rekall/issues).

In order to help us solve your issues as quickly as possible,
please include the following information when filing a bug:

* The version of rekall you're using.
* The operating system used to run rekall.
* The version of python used to run rekall.
* The suspected operating system of the memory image.
* The complete command line you used to run rekall.
* Please run Rekall with the -v flag and attach the output.

## History

In December 2011, a new branch within the Volatility project was created to
explore how to make the code base more modular, improve performance, and
increase usability. The modularity allowed Volatility to be used in GRR, making
memory analysis a core part of a strategy to enable remote live forensics.  As a
result, both GRR and Volatility would be able to use each others’ strengths.

Over time this branch has become known as the "scudette" branch or the
"Technology Preview" branch.  It was always a goal to try to get these changes
into the main Volatility code base.  But, after two years of ongoing
development, the "Technology Preview" was never accepted into the Volatility
trunk version.

Since it seemed unlikely these changes would be incorporated in the future, it
made sense to develop the Technology Preview branch as a separate project. On
December 13, 2013, the former branch was forked to create a new stand-alone
project named "Rekall.” This new project incorporates changes made to streamline
the codebase so that Rekall can be used as a library. Methods for memory
acquisition and other outside contributions have also been included that were
not in the Volatility codebase.

Rekall strives to advance the state of the art in memory analysis, implementing
the best algorithms currently available and a complete memory acquisition and
analysis solution for at least Windows, OSX and Linux.