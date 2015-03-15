To build one of these up you require one of the PCB's I have had produced, and then the components that are listed in the BOM (Bill of materials).
Unfortunately I can't offer to build one for you, or supply the components, you will have to sort this out yourself. The BOM contains links to where
you can obtain the components. As I am in the UK most of the links are UK based.

The schematic and BOM is in the SVN repository. See here DevelopmentSoftware for the software to download them, and the software to view the schematic.

One of the items on the BOM you may already have, the RF module itself. The original transmitters from some of the models this module is intended for contain said RF module.
This sometimes can be removed and used in this project. For pictures of the various transmitter internals see the links in the table below. The original Hubsan X4 doesn't have a module that can be reused as it is part of the main PCB, therefore the below option is your only option.<br>

If you don't want to disassemble your original transmitter you can by an RF module <a href='http://www.aliexpress.com/item/A7105-Wireless-RF-2-4GHz-Transceiver-Module-3-3V-NRF24L01-SI4432-10dBm-64mA-20mA/619869938.html'>here</a> from AliExpress. It claims to have 500 meter range, but reports have it as not quite that far. Looks like this:<br>
<br>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/aliexpress_a7105_module.jpg' border='0'>

It fits directly into the 9 pin RF module header.<br>
<br>
This table contains the pinouts for suitable RF modules as used in the original transmitters. Looking at the component side of the module pin 1 is left most.<br>
<br>
<table><thead><th>RF Module</th><th>Pin 1</th><th>2</th><th>3</th><th>4</th><th>5</th><th>6</th><th>Notes</th></thead><tbody>
<tr><td><a href='http://code.google.com/p/rc-ppm-2-spi/wiki/HardwareJPTwisterQuadTx'>JP Twister quad</a></td><td>CS</td><td>CLK</td><td>IO</td><td>NA</td><td>GND</td><td>3.3v</td><td>Direct plug in</td></tr>
<tr><td><a href='http://code.google.com/p/rc-ppm-2-spi/wiki/HardwareV929Tx'>WL Toys V929</a></td><td>CS</td><td>CLK</td><td>IO</td><td>NA</td><td>GND</td><td>3.3v</td><td>Direct plug in</td></tr>
<tr><td><a href='http://code.google.com/p/rc-ppm-2-spi/wiki/HardwareHCW553Tx'>HCW553</a></td><td>CS</td><td>CLK</td><td>IO</td><td>NA</td><td>GND</td><td>3.3v</td><td>Direct plug in</td></tr>
<tr><td><a href='http://code.google.com/p/rc-ppm-2-spi/wiki/HardwareSymaX1Tx'>Syma X1</a></td><td>CS</td><td>CLK</td><td>IO</td><td>NA</td><td>3.3v</td><td>GND</td><td>Polarity reversed, needs flying wires</td></tr></tbody></table>

The first three will plug straight into the 6 pin socket on the modules PCB and work without problem. The Syma X1 RF module has the GND and 3.3v pins<br>
reversed so if you plug it in you will fry it. You can still use it but to do so you will have to omit the 6 pin socket from the build and connect to it using flying wires from the module<br>
PCB to the RF pcb, and make sure you get the ordering correct.<br>

The PCB involves surface mount components. A lot of people will now be ruling this project out because they can't do surface mount ! If however you are a competent through<br>
hole solderer then I would say you absolutely can do surface mount. The prototype PCB was hand soldered using this lot:<br>
<br>
<ul><li>Antex TCS230 soldering iron <a href='http://www.antex.co.uk/soldering/standard-soldering-irons/tcs230/'>http://www.antex.co.uk/soldering/standard-soldering-irons/tcs230/</a> <br>
</li><li>0.5mm tip <a href='http://www.antex.co.uk/soldering/replacement-bits/1100-series-bits/b110560/'>http://www.antex.co.uk/soldering/replacement-bits/1100-series-bits/b110560/</a> <br>
</li><li>Flux <a href='http://cpc.farnell.com/warton/315-0-5l-bottle/315-noclean-flux-1-2-litre/dp/SD00085'>http://cpc.farnell.com/warton/315-0-5l-bottle/315-noclean-flux-1-2-litre/dp/SD00085</a> <br>
</li><li>Tip cleaner <a href='http://cpc.farnell.com/jsp/search/productdetail.jsp?SKU=SD01015'>http://cpc.farnell.com/jsp/search/productdetail.jsp?SKU=SD01015</a> <br>
</li><li>0.3mm leaded solder (This is the oddest item in my setup, it's not easy to get a hold of but very much worth the effort) <a href='http://www.ebay.co.uk/itm/160619728934'>http://www.ebay.co.uk/itm/160619728934</a> <br>
</li><li>Magnifying glass <a href='http://www.shesto.co.uk/p218/Flexi-Neck-Magnifier/product_info.html'>http://www.shesto.co.uk/p218/Flexi-Neck-Magnifier/product_info.html</a> <br>
</li><li>120mm LED ring stuck to above magnifier <a href='http://www.ebay.co.uk/itm/111019086879'>http://www.ebay.co.uk/itm/111019086879</a> <br>
</li><li>Tweezers  <a href='http://www.shesto.co.uk/p100/%237-Stainless-Steel-Tweezers/product_info.html'>http://www.shesto.co.uk/p100/%237-Stainless-Steel-Tweezers/product_info.html</a> <br>
</li><li>Loupe (x40 apparently although I doubt it, and LED lit) <a href='http://www.ebay.co.uk/itm/350773512491'>http://www.ebay.co.uk/itm/350773512491</a> <br>
</li><li>Desoldering braid (always handy) <a href='http://cpc.farnell.com/servisol/200004375/soldamop-green-2-5mm-x-10m/dp/SD00667'>http://cpc.farnell.com/servisol/200004375/soldamop-green-2-5mm-x-10m/dp/SD00667</a></li></ul>

Solder the physically shorter surface mount components in first, then the taller surface mount ones, then finish with the through hole ones.<br>
<br>
To do the surface mount components put a drop of flux on the pcb and a tiny amount of solder on the tip of the iron.<br>
<br>
For the sub 10 pin packages hold the component in place with the tweezers, and dab the iron on one pin/pad. Then solder the other pins as you would solder anything else.<br>
<br>
For the processor dab the iron on a couple of opposite pins/pads just to make sure it can't move, then solder the other pins as you would solder anything else.<br>
<br>
If you end up with an ulgy looking "dab" joint just go back and reflow it with some flux and/or solder once you have done the others.<br>
<br>
The pin pitch of the processor is large enough that you can easily solder it pin by pin.<br>
<br>
Use the loupe to examine your joints in detail as you see fit.<br>
<br>
Use the solder braid to remove any solder bridges.<br>
<br>
Here are a couple of videos of myself doing some SMT soldering. They feature the Gruvin9x replacement PCB for the 9x transmitter, but the techniques are the same. As mentioned you can solder the whole ppm-2-spi board pin by pin (the pin pitch on the PCB is larger than on the Gruvin9x board), so the first video is probably more use.<br>
<wiki:gadget url="http://rc-ppm-2-spi.googlecode.com/svn/wiki/gcVideo.xml" up_video="https://vimeo.com/108601753" width="640" height="384"/><br>
<br>
<wiki:gadget url="http://rc-ppm-2-spi.googlecode.com/svn/wiki/gcVideo.xml" up_video="https://vimeo.com/108526858" width="640" height="384"/>