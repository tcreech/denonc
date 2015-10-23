# denonc
Tim Creeech <tcreech@umd.edu>

Standalone, UNIXy, interactive or scriptable CLI interface for Denon receivers.


## Purpose
This is a simple wrapper implementing the communication below the Denon AVR
control protocol. Allows for interactive input (in which case a prompt is
displayed) or piped/redirected input for scripting. Note that this uses
'readline', which means that the interactive input will obey your .inputrc.

## What will this work with?
This is not specific to any particular AVR control protocol version or
receiver. If you have the protocol document for your receiver in front of it
you can punch in commands exactly as you see them. It should hopefully work
with most networked Denon receivers.

## Examples
### Interactive usage
Ask whether the reciever is powered on:

    $ denonc denon-receiver.lan
    > PW?
    PWON
    >
The receiver is powered on.

### Programmatic usage
Say your Denon has the host name "denon". We can increase the master volume:

    $ echo MVUP | denonc
    MV38
    MVMAX 71
The master volume level is now at 38 out of 71.
