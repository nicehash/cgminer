##################################################
#author: Novak                                   #
#email: novak@gekkoscience.com                   #
#BTC address: 1NovakVK1FWdh9gs41dckVQS8bxSzwiaRw #
##################################################

You may compile compac support with the ./configure option --enable-gekko.
You can set the clock speed between 100 and 500 MHz using the --compac-freq option, do not expect it to run over about 150MHz on stock USB power (depending on voltage and the individual stick).

There is an example file showing usage: cgminer_run.sh
Usage:
./cgminer --compac-freq <num>

<num> is any integer from 100 to 500.

You can calculate the expected hashrate as 0.055*(clock_in_mhz)=GH/s.  For example, 200 MHz gives 11GH/s.

--
novak

## add from wareck : ##
before compile edit usbutil.c en go to line 932
If you use original Gekko usb stick (green) uncomment line "GekkoScience"
if you use bitshopper usb stick (black) uncomment line "bitshopperde"
(only one line per time, I'm working on a new file wich allow working together)

#ifdef USE_GEKKO
	{
		.drv = DRIVER_gekko,
		.name = "GEK",
		.ident = IDENT_GEK,
		.idVendor = 0x10c4,
		.idProduct = 0xea60,
		.iManufacturer = "bitshopperde",
		//.iManufacturer = "GekkoScience",
		.iProduct = "Compac BM1384 Bitcoin Miner",
		.config = 1,
		.timeout = GEKKO_TIMEOUT_MS,
		.latency = LATENCY_UNUSED,
		INTINFO(amu_ints) },
#endif

wareck:wareck@gmail.com