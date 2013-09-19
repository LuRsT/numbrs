# numbrs

See the line numbers of whathever it is that's going on in STDOUT by piping it to `numbrs`.

## Instalation:

The only requirement for this script is perl, which, if you're using Linux, you most certainly
already have.
Just put the file in one of the many paths that your `$PATH` already has, hopefully, you'll have
write access to one of them to put the file there and give it execution permission, basically this:

    $ mv numbrs ~/bin
    $ chmox +x ~/bin/numbrs

## Example usage:

### Number `ls` output:

    $ ls -1
    README.md
    numbrs
    $ ls -1 | numbrs
    1 README.md
    2 numbrs

### Number `grep` output:

    $ grep "num" README.md | numbrs
    1 numbrs
    2 See the line numbers of whathever it is that's going on in STDOUT by piping it to `numbrs`.
    3     cat numbrs | ./numbrs
    4     numbrs
    5     $ ls -1 | numbrs
    6     2 numbrs

### Number `cat` output:

    $ cat numbrs | numbrs
     1 #!/usr/bin/perl
     2
     3 use strict;
     4 use warnings;
     5
     6 my @ARGV    = <STDIN>;
     7 my $counter = 1;
     8 my $size    = length scalar @ARGV;
     9
    10 for my $i (@ARGV) {
    11     printf("%${size}d %s", $counter, $i);
    12     $counter += 1;
    13 }

