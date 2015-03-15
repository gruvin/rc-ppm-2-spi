See [ModelSetups](ModelSetups.md) for some pre done opentx model setup files.

# PPM Setup #

The module takes a negative PPM signal with 1000us as bottom stick and 2000us as top stick. With 1500us being treated as centre. Please set your transmitter according.
If the module detects pulses outside these ranges it will limit them to between 1000us and 2000us

Correct channel order with JP2 open is: AIL ELE THR RUD <br>
Correct channel order with link JP2 closed is: THR AIL ELV RUD<br>
<br>
<h1>Module Protocol Selection</h1>

The module can operate in three modulation modes, they are:<br>
<br>
<ul><li>FlySky<br>
</li><li>FlySky modified for various quadcopters<br>
</li><li>Hubsan X4</li></ul>

Which mode is selected is controlled by the position of channel 8 at the time of switch on. Any change<br>
in channel 8 after this time is ignored. This is a safety feature to stop you changing mode mid flight.<br>
<br>
Each mode will light a combination of LEDS to indicate which mode is in use.<br>
<br>
The approximate pulse widths and LED combos for the various modes are:<br>
<pre><code><br>
1000us -&gt; 1143us FlySky             RED<br>
1144us -&gt; 1286us FlySky Mod         YELLOW<br>
1287us -&gt; 1429us Hubsan             GREEN</code></pre>
Several other modes exists, some are reserved for future protocols and one we will discuss later, they are:<br>
<pre><code><br>
1430us -&gt; 1572us Reserved           RED + YELLOW<br>
1573us -&gt; 1715us Reserved           YELLOW + GREEN<br>
1716us -&gt; 1858us Reserved           RED + GREEN<br>
1859us -&gt; 2000us Change module ID   RED + GREEN + YELLOW LEDS FLASHING</code></pre>
Selecting one of the reserved slots will cause the module to stop. You will need to select another mode and cycle the power to restore operation.<br>
<br>
If using OpenTx I recommend you setup a mixer on channel 8 using MAX as the source, and the weight figure to set the position of channel 8<br>
and therefore the mode of the module. This then allows you to lock each model memory to the correct modulation for the model. Like so:<br>
<br>
<img src='http://rc-ppm-2-spi.googlecode.com/svn/wiki/images/channel8_mixer.jpg' border='0'>

If you do this then approximate values for the modes are:<br>
<br>
<pre><code><br>
-100 -&gt; -71  FlySky             RED<br>
-70  -&gt; -42  FlySky Mod         YELLOW<br>
-41  -&gt; -13  Hubsan             GREEN<br>
-12  -&gt; +16  Reserved           RED + YELLOW<br>
+17  -&gt; +45  Reserved           YELLOW + GREEN<br>
+46  -&gt; +74  Reserved           RED + GREEN<br>
+75  -&gt; +100 Change module ID   RED + GREEN + YELLOW LEDS FLASHING</code></pre>

<h1>Binding</h1>

Binding is initiated in either of the FlySky modes by simply holding down the bind button at switch on. The orange LED<br>
will light to indicate bind mode. <br>
As soon as it is lit you can release the bind button. The module will stay in binding mode<br>
for several seconds then default to normal transmission. You have this window to bind your model.<br>
<br>
Binding in Hubsan mode happens at every switch on regardless of the bind button. This is a quirk of the Hubsan protocol. Again the orange LED will light to show binding is taking progress. However as the Hubsan protocol is a two way protocol the module knows when a successful binding has taken place and will only extinguish the orange LED when this has happened.<br>
<br>
<h1>Module ID</h1>

The ID for the module is chosen randomly the first time you switch it on. It is then stored in the processors internal EEPROM and used from then on. If you wish to keep this ID at subsequent re-flashing of the firmware you need to enable the EESAVE fuse on the ATMEGA.<br>
<br>
If you wish to change this ID to another randomly chosen one then:<br>
<br>
<ul><li>Switch on your Tx<br>
</li><li>Set channel 8 to 1859us - 2000us<br>
</li><li>Switch off your transmitter then switch it back on<br>
</li><li>When you switch back on the RED + GREEN + YELLOW leds will start flashing. At this point the ID hasn't changed.<br>
</li><li>Next set channel 8 to represent the mode you wish the module to be in for the model you are flying (doing this now will save you another power cycle). ID is still unchanged at this point.<br>
</li><li>Press and hold the bind button until the RED + GREEN + YELLOW leds remain solid on. This confirms the change.<br>
</li><li>As soon as you release the button the module will reboot and lock the change in.</li></ul>

<h1>Extra features of "FlySky mode for various quadcopters"</h1>

The FlySky mode that is modified for various quadcopters has some extra features.<br>
<br>
<ul><li>Setting channel 5 above 1540us sets bit 13 of the rudder channel. On my JP Twister Quad with toggles the LEDS</li></ul>

<ul><li>Setting channel 6 above 1540us sets bit 14 of the throttle channel Apparently this toggles the use of the video camera on some machines. (I have not tested this)</li></ul>

<ul><li>Setting channel 7 above 1540us sets bit 15 of the throttle channel. Apparently this toggles the use of the still camera on some machines. (I have not tested this)</li></ul>

Be very careful when playing with channel 6 and 7, as you can see they effect the throttle channel so are perfectly capable of giving<br>
you unexpected motor starts if used with the wrong model.<br>
<br>
With both FlySky protocols channel 8, the one used to select the transmission mode is also transmitted as channel 8. I know this means you<br>
lose the use of channel 8 but it was done to enable a greater range of transmitter to use the module.<br>
<br>
<h1>Extra Features of the Hubsan protocol</h1>

<ul><li>Setting channel 5 above 1540us will switch the LEDs on.</li></ul>

<ul><li>Setting channel 6 above 1540us will enable the flip inhibit mode.</li></ul>

Think that covers it.