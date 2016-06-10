# msync

Simple command-line tool to synchronize mtimes on matching files in different directory trees

If you use [Unison](https://www.cis.upenn.edu/~bcpierce/unison/)
 you may have encountered situations where a program you use updates the mtimes of several thousand files without actually changing the content,
 which means you have to wade through several thousand `props` changes to find a few content changes.
If you would rather keep the oldest mtime of the content than tell Unison to ignore mtimes,
 this tool can help.

msync currently also preserves atimes at the expense of changing ctimes.
The issue is that accessing files to compare them can trigger an update to their atimes, which may be unwanted,
 but restoring the original atimes will trigger an update to their ctimes.
Future releases may provide options to change this behavior.

### Dependencies

 * [Ruby](https://www.ruby-lang.org/)

### Installation

Copy the `msync` executable to some appropriate location like `~/bin/`, preferably in your $PATH, and make sure it's marked as executable.

### Usage

`msync [dir1] [dir2] ...`

### License

msync - Simple command-line tool to synchronize mtimes on matching files in different directory trees<br/>
Copyright © 2016 Shad Sterling <<me@shadsterling.com>>

This program is free software: you can redistribute it and/or modify it under the terms of the
GNU Affero General Public License as published by the Free Software Foundation,
either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY;
without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
See the GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License along with this program.
If not, see <http://www.gnu.org/licenses/agpl.html>


