XCode File Templates - Guidelines Compliant
===========================================

XCode 4 File Templates compliant with the Google Objective-C Style Guide.

Introduction
------------

XCode 4 provides template files (used when creating a new file or adding code,
f.e. by linking a new outlet or action) which are not compliant with the
[Google Objective-C Style Guide](http://google-styleguide.googlecode.com/svn/trunk/objcguide.xml),
most notably, they use 4 spaces for tabs and open brackets on new lines.
This might cause unexpected behavior in
XCode, which won't follow your custom indentation settings.

The included templates use **2 spaces** for indentation
and put **opening brackets on the same line** as declarations.

Installation
------------
Simply clone this repository into

    ~/Library/Developer/Xcode/Templates/File Templates
    
or in case you already have custom templates, clone this repo anywhere
on your disk and then copy files from there into the given path.

In case you're using Finder and can't find <user>/Library,
you will need to unhide it:

    chflags nohidden ~/Library

Tools
-----
In case you already have files with brackets on new lines, you can run
this PERL command line script

    perl -0777 -pi -w -e 's/\n{/ {/g;' *.m

which strips the new lines in all .m files in the current directory.

If you have a whole folder structure full of source code formatted
this way, this script
   
    perl -0777 -pi -w -e 's/\n{/ {/g;' `find ./ -name *.m`

will work on current directories and all directories, as long as the
paths don't include any spaces. If you know how to fix this, let me
know.

Errors
------
If you encounter an error or code that doesn't comply with the Style Guide,
send me a pull request or pop an email.
