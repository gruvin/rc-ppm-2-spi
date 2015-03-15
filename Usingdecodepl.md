You are going to need one of these <a href='http://www.saleae.com/logic/'>logic analysers</a> an <a href='http://www.perl.org/get.html'>install of perl<a> and this <a href='http://rc-ppm-2-spi.googlecode.com/svn/trunk/spi_parser/decode.pl'>script</a>

I will presume you know how to install perl and use your logic analyser.<br>
<br>
Just follow the pics:<br>
<br>
<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_01.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_01_sml.jpg' border='0'> <a>
<br>Capture some data you want to look at. Channel order should be:<br>
0 : Enable<br>
1 : Clock<br>
2 : MOSI<br>
3 : MISO (If used)<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_02.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_02_sml.jpg' border='0'> <a>
<br>We need to add an SPI protocol decoder.<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_03.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_03_sml.jpg' border='0'> <a>
<br>Give it these settings. The odd one being "4 Bits per Transfer".<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_04.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_04_sml.jpg' border='0'> <a>
<br>If you zoom in you should see something like this.<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_05.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_05_sml.jpg' border='0'> <a>
<br>Now lets export the data.<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_06.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_06_sml.jpg' border='0'> <a>
<br>Give it a name and save it.<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_07.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_07_sml.jpg' border='0'> <a>
<br>The saved data should look like this if opened.<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_08.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_08_sml.jpg' border='0'> <a>
<br>Open up a command prompt in the directory you just saved the exported data to and run the command shown.<br>

<a href='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_09.jpg'>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/decoding/perl_09_sml.jpg' border='0'> <a>
<br>Open text.txt in a text editor and you should see this.<br>
WR means write to A7105, RD means read from A7105. Register names are shown along with register number and data transferred.