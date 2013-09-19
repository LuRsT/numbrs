numbrs
======

See the line numbers of whathever it is that's going on in STDOUT by piping it to `numbrs`.

    cat numbrs | ./numbrs
     0 #!/usr/bin/perl
     1
     2 use strict;
     3 use warnings;
     4
     5 my @ARGV    = <STDIN>;
     6 my $counter = 0;
     7 my $size    = length scalar @ARGV;
     8
     9 for my $i (@ARGV) {
    10     printf("%${size}d %s", $counter, $i);
    11     $counter += 1;
    12 }

