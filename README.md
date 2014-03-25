York nextbus
============

`nextbus` is a simple command line script to check the next arriving bus on
York, UK.  It uses live information grabbed from [this
webpage](http://deps.at/?32903631).  Works like this:

	$ nextbus
	3 min

For the next buses, pass the verbose flag `-v`:

	$ nextbus -v
	Theatre Film & Television [QR/NFC]                    
	Departures for: 25 Mar 2014 at 16:21                  
	Service  Destination                  Stop  Time
	44       York Rail Station            opp   3 min
	44       York Rail Station            opp   18 min
	44       York Rail Station            opp   16:54
	44       York Rail Station            opp   17:12

To configure which bus stop you want, edit the source with the bus stop code.
The default is `32903631`: Theatre Film & Television, opposite side, bound to
the city center:

	BUSSTOP=<code>

To know the code of your bus stop, just scan the QR code located there.


Notice
------

When using the script inside a widget or by your window manager, try to *call
it in intervals larger than a minute* so you *don't overload* the server.


Known bugs
----------

This readme is longer than the code.

