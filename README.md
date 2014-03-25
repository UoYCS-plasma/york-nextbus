York nextbus
============

`nextbus` is a simple command line script to check the arrival time of next bus
on York, UK.  It uses live information grabbed from [this
webpage](http://deps.at/?32903631).  Works like this:

	$ nextbus
	3 min

For a list of arrivals, pass the verbose flag `-v`:

	$ nextbus -v
	Theatre Film & Television [QR/NFC]                    
	Departures for: 25 Mar 2014 at 16:21                  
	Service  Destination                  Stop  Time
	44       York Rail Station            opp   3 min
	44       York Rail Station            opp   18 min
	44       York Rail Station            opp   16:54
	44       York Rail Station            opp   17:12

To configure which bus stop you want, edit the line containing `BUSSTOP=<code>`
with the desired bus stop code.  The default is `32903631`: Theatre Film &
Television, opposite side, bound to the city center.

To know the code of your bus stop, just scan the QR code located there.


Notice
------

When using the script inside a widget or by your window manager, try to *call
it in intervals larger than a minute* so you *don't overload* the server.

You can use [ched] tool to make subsequent calls to nextbus cached:

    ched -t 60 nextbus

By running line above you'll never exceed a request per minute on the server.



Known bugs
----------

This readme is longer than the code.


[ched]: https://github.com/rudymatela/evenmoreutils
