# Linux-Task-1


Write a script renaming files by inserting a suffix to the file name before the file's extension. For example, if the suffix is "sfx", the renaming should be done in the following way: 

"a" -> "asfx"
"a.txt" -> "asfx.txt"
"abc.doc" -> "abcsfx.doc"
"abc.txt.doc" -> "abc.txtsfx.doc"
, etc. The suffix is the first script argument followed by the renamed file list.

Syntax:
./insert_suffix [-d] [-v] [-h] [--] sfx files...
 The script should support the following options (keys):
 -h print help message (usage, command syntax, supported options, and arguments)
 -d "dry run", print old and new file names without actual renaming
 -v print old and new names of renamed files (without the options script act silently)
 -- option and suffix/file names separator

Take into account that filenames and the suffix may contain shell metacharacters including wildcards and start with a minus sign char (-).

Execution examples:
./insert_suffix -d sfx file*.txt
(add sfx as a suffix to all files in current directory with .txt extension, dry run)
./insert_suffix -v sfx -- *
(add sfx as a suffix to all files in the current directory, verbose run, make sure that files started with - are also renamed correctly)
./insert_suffix -- -v *

(add -v as a suffix to all files in the current directory, silent run, make sure that files started with - are also renamed correctly) and so on.

The script should correctly handle argument and option syntax errors (absence of the suffix or filenames, incorrect options, etc, printing a corresponding error message to the error stream and stopping execution with non-zero status).

