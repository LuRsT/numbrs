numbrs
======

See the line numbers of whathever it is that's going on in STDOUT by piping it to `numbrs`.

    cat numbrs | ./numbrs
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

