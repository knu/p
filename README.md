# p - a lazy wrapper for `$PAGER`

## NAME

`p(1) - a lazy wrapper for $PAGER`

## SYNOPSIS

```
p
p ...
```

## DESCRIPTION

`p(1)` is a lazy wrapper for `$PAGER`.  When invoked as a piped pager
(i.e. the standard input is not a terminal) without a file argument,
it delays a pager invocation until it gets more lines than are
displayable in the current terminal.  The line number limit is
estimated by subtracting two from the terminal's height to leave room
for shell prompts.

If any argument is given or the standard input is a terminal, it
becomes eager enough to delegate everything to the pager.  This means
calling `p` with a `-` (`... | p -`) always invokes the pager even if
it gets small input.

Lastly, if the standard output is not a terminal, it just passes the
standard input through to the standard output without calling a pager.

## ENVIRONMENT

- `PAGER`

    The command (or command line) wrapped around and invoked by this
    wrapper.

## SEE ALSO

[`less(1)`](http://www.freebsd.org/cgi/man.cgi?query=less&sektion=1)

## AUTHOR

Copyright (c) 2012 Akinori MUSHA.

Licensed under the 2-clause BSD license.  See `LICENSE.txt` for
details.

Visit [GitHub Repository](https://github.com/knu/p) for the latest
information.
