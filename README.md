pifacedigitalio
===============

The PiFace Digital Input/Output module.

*The PiFace Digital IO module uses Python 2 and is incompatible with Python 3*

Depends on [spipy](https://github.com/tompreston/spipy).

Examples
=======
    >>> import pifacedigitalio as p
    >>> p.init()       # initialises the PiFace Digital board 
    >>> p.init(False)  # same as above w/out resetting ports

    >>> p.digital_write(0, 1)    # writes pin0 (board0) high
    >>> p.digital_write(5, 1, 2) # writes pin5 on board2 high
    >>> p.digital_read(4)        # reads pin4 (on board0)
    >>> p.digital_read(2, 3)     # reads pin2 (on board3)

    >>> led0 = p.LED(0)  # create an LED object (pin0, board0)
    >>> led0.turn_on()   # turn on the LED
    >>> led0.value = 1   # turn on the LED

    >>> led3_2 = p.LED(3, 2)  # create an LED object (pin3, board2)
    >>> led3_2.turn_on()      # turn on the LED

    >>> switch2 = p.Switch(2) # create a Switch object (pin2, board0)
    >>> switch2.value         # is the switch pressed?
    0
    >>>

    >>> class Chicken(pfio.Relay):
    ...     def __init__(self):
    ...         pfio.Relay.__init__(self, 0)
    ...     def wobble(self):
    ...         self.turn_on()
    ...
    >>> chick1 = Chicken()
    >>> chick1.wobble()      # Turns on relay0 (connected to a robot chicken)
