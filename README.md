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
	Departures for: 25 Sep 2015 at 14:43
	Service  Destination                  Stop  Time
	66       City Ctr & Rail Stn          opp   14:56
	66       City Ctr & Rail Stn          opp   25 min
	66       City Ctr & Rail Stn          opp   15:26
	66       City Ctr & Rail Stn          opp   55 min

To configure which bus stop you want, edit the line containing `BUSSTOP=<code>`
with the desired bus stop code.  The default is `32903631`: University of York,
Theatre Film & Television, opposite side, bound to the city center.

To know the code of your bus stop, just scan the QR code located there.


Dependencies
------------

* bash, grep and sed, which probably you have installed;
* [links], a text WWW browser.
	Install with `apt-get install links` or `pacman -S links`.


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
[links]: http://links.twibright.com
