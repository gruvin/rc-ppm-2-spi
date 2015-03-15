Once you have the module built you need to flash the firmware. The pre-compiled firmware is already available in the SVN repository, it's called <a href='http://rc-ppm-2-spi.googlecode.com/svn/trunk/code/default/ppm2spi.hex'>ppm2spi.hex.</a> <br>

You will need an AVR programmer such as the Atmel AVR ISP MkII <a href='http://www.atmel.com/tools/AVRISPMKII.aspx'>http://www.atmel.com/tools/AVRISPMKII.aspx</a> usually about 30GBP, you can then use <a href='http://www.atmel.com/tools/STUDIOARCHIVE.aspx'>AVR Studio version 4.xx</a> to flash the firmware.<br>
<br>
I know I lot of much cheaper programmers are available <a href='http://www.hobbyking.com/hobbyking/store/uh_viewitem.asp?idproduct=21321'>http://www.hobbyking.com/hobbyking/store/uh_viewitem.asp?idproduct=21321</a> and you can use AVRDude <a href='http://download.savannah.gnu.org/releases/avrdude/'>http://download.savannah.gnu.org/releases/avrdude/</a> with them. But I have never been a fan, so this guide won't show them.<br>
<br>
Just follow the pics:<br>
<br>
<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_01.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_01_sml.jpg' border='0'> <a>
<br>Connect things up and power up. Observe correct ISP connector orientation.<br> <b>NOTE The first time you flash your module no LEDs will be on, they are only on in the pic as this module has been flashed before.</b>
<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_02.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_02_sml.jpg' border='0'> <a>
<br><br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_03.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_03_sml.jpg' border='0'> <a>
<br>Start AVR Studio and then the programmer interface.<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_04.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_04_sml.jpg' border='0'> <a>
<br>The first time you flash the blank chip you will need to adjust the ISP frequency right down to 125Khz, this is because the stock processor is only clocked at 1Mhz and the ISP frequency must be a factor of 4 below this. Set the "ISP Freq" first then click "Write"<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_05.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_05_sml.jpg' border='0'> <a>
<br>Set the correct processor type.<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_06.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_06_sml.jpg' border='0'> <a>
<br>Check everything is OK so far. Click "Read Signature". You should see an "OK" down below.<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_07.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_07_sml.jpg' border='0'> <a>
<br>Next set the fuses. Enter 0xFF for the EXTENDED fuse, 0xD1 for the HIGH fuse, and 0xCE for the LOW fuse, then click "Program"<br>


<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_08.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_08_sml.jpg' border='0'> <a>
<br>Now you can speed up the ISP frequency.<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_09.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_09_sml.jpg' border='0'> <a>
<br>Click the three dots...<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_10.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_10_sml.jpg' border='0'> <a>
<br>Select the spi2ppm.hex file you downloaded in the "Flash - Input HEX File" box.<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_11.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/prog/prog_11_sml.jpg' border='0'> <a>
<br>Click program and wait while it's uploaded. Then your done<br>

Next time you update the firmware you can ignore the steps for setting fuses and altering ISP frequency.