<b>Q: What's this all about then ?</b><br>
<b>A:</b> It's a transmitter module to allow you to fly some of the cheap RTF<br>
aircraft (that will usually only work with the transmitter they are supplied<br>
with) on any transmitter that will take a JR module.<br>

<b>Q: Does it support Spektrum, or Walkera, or Nine Eagles, or FrSky, or V202, or Skyartec protocols ?</b><br>
<b>A:</b> No, the hardware can't do these protocols.<br>
<br>
<b>Q: Can I use an RF module with the CC2500 chip, or the CYRF6936 chip, or the NRF24L01 chip ?</b><br>
<b>A:</b> No, only the A7105 chip.<br>

<b>Q: Does it use Arduino ?</b><br>
<b>A:</b> No. For early development I used an ATMega that happened to be on an Arduino board, but no Arduino code was or is used. No bootloader, no anything. <br>

<b>Q: What models does it work with ?</b><br>
<b>A:</b> Personally tested with Hubsan X4, JP Twister Quad.<br>
<b>A: </b>Others tell me it works with WLToys v929, WLToys V939, Syma X1, and<br>
HCW553 <br>

<b>Q: I can fly some of the models you mention with a stock FlySky module, so<br>
why do I need this module ?</b><br>
<b>A: </b>Some of the more advanced features these models have, such as the flip<br>
button, turning cameras on and off, and turning LEDs on and off won't work with<br>
the stock FlySky module. Also it won't fly Hubsan X4's.<br>
<br>
<b>Q: Can it support xxx model ?</b><br>
<b>A:</b> If it uses the A7105 chipset then with some software work, yes.<br>
However if it's a new protocol and therefore the protocol requires decoding then<br>
either you are going to have to do it yourself and code it yourself or buy me<br>
one of the models to examine.  SEE NOTE BELOW<br>
<br>
<b>Q: So how long to decode a protocol if I buy you a model ?</b><br>
<b>A: </b>You might be quicker to do it yourself.<br>
<br>
<b>Q: But I don't know any programming or electronics.</b><br>
<b>A: </b>Probably still quicker to do it yourself :)<br>
<br>
<b> NOTE</b><br>
If however the protocol code already exists in deviation firmware<br>
<a href='https://bitbucket.org/PhracturedBlue/deviation/overview'>
<a href='https://bitbucket.org/PhracturedBlue/deviation/overview'>https://bitbucket.org/PhracturedBlue/deviation/overview</a></a> it is much easier to<br>
port over, but to test it I would still need a sample of the model in question.<br>
The code can be ported without testing but runs a high risk of being useless, to<br>
the point where it is not worth spending time on it in the first place.<br>
<br>
<b>Q: What about supporting other chipsets ?</b><br>
<b>A:</b> I personally have no need for other chipsets at the minute so right<br>
now it's zero priority.<br>
<br>
<b>Q: Where is the schematic, BOM, or firmware HEX ?</b><br>
<b>A:</b> It's in the SVN repository, see wiki page DevelopmentSoftware for the<br>
software to download it and view it. <br>
<b>A:</b> Or check the project home page for some direct links to the files.<br>
<br>
<br>
<b>Q: How would one use the DEBUG1/DEBUG2 pins ?</b><br>
<b>A: </b>They currently just toggle to show various timing within the software,<br>
for use on an oscilloscope.<br>