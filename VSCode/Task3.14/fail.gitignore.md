[<contents](./readme.md)

## Fail.gitignore

---
---


Often, you’ll have a class of files that you don’t want Git to automatically add or even show you as being untracked. These are generally automatically generated files such as log files or files produced by your build system. In such cases, you can create a file listing patterns to match them named .gitignore. Here is an example .gitignore file:

`$ cat .gitignore`

`*.[oa]`

`*~`

The first line tells Git to ignore any files ending in “.o” or “.a” — object and archive files that may be the product of building your code. The second line tells Git to ignore all files whose names end with a tilde (~), which is used by many text editors such as Emacs to mark temporary files. You may also include a log, tmp, or pid directory; automatically generated documentation; and so on. Setting up a .gitignore file for your new repository before you get going is generally a good idea so you don’t accidentally commit files that you really don’t want in your Git repository.

The rules for the patterns you can put in the *.gitignore* file are as follows:

- Blank lines or lines starting with # are ignored.

- Standard glob patterns work, and will be applied recursively throughout the entire working tree.

 - You can start patterns with a forward slash (/) to avoid recursivity.

- You can end patterns with a forward slash (/) to specify a directory.

- You can negate a pattern by starting it with an exclamation point (!).

Glob patterns are like simplified regular expressions that shells use. An asterisk (*) matches zero or more characters; [abc] matches any character inside the brackets (in this case a, b, or c); a question mark (?) matches a single character; and brackets enclosing characters separated by a hyphen ([0-9]) matches any character between them (in this case 0 through 9). You can also use two asterisks to match nested directories; a/**/z would match a/z, a/b/z, a/b/c/z, and so on.

Here is another example *.gitignore* file:

`# ignore all .a files`

    *.a

``# but to track lid.a even though you`re ignoring .a files above``

    !lib.a

`# only ignore the TODO file in the current directoiry, not subdir/TODO`

    /TODO    

`# ignore all files in any directory named duild`

    build/

`# ignore doc/notes.txt, but not doc/server/arch.txt`

    dox/*.txt

``# ignore all. pdf files in the doc/ directory and any of it`s directories``

    doc/**/*.pdf


___
**Tip**:

GitHub maintains a fairly comprehensive list of good .gitignore file examples for dozens of projects and languages at https://github.com/github/gitignore if you want a starting point for your project.
___