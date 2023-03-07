# RazerSDKjs-3.0
A (javascript) library that makes it easy to create Razer Chroma effects, build on websocket (comes with build-in function to display text)
<br />
Try the web simulator if you like! <a href="https://github.com/bimsie20-IT/RazerSDKjs-3.0/blob/main/RazerChroma%20Web-Simulator.zip">Razer Chroma Preview</a>

<br />
<br />
<br />

# Documentation

<h3>Initialization</h3>
<pre>
<code>
// Creating an object called 'chroma'
let chroma = new RazerSDKjs({
    applicationName: {name of your application},
    description: {description of your application},
    developer: {developer},
    contact: {your contact information (GitHub page)}
});
<br />
<br />
<br />
// Creating a connection with the WebSocket
chroma.createSession().then(
<br />
    // If a connection was established
    function(APIsocket) {
<br />
        // YOUR CODE
        // FROM HERE FOLLOWS THE REST OF THE REST OF THE DOCUMENTATION
<br />
    }
<br />
    // If a connection could not be established
    function(error) {
        window.alert('Razer Synapse with connect plugin was not dedected');
    }
<br />
);
</code>
</pre>

<br />
<br />
<br />

<h3>Uninitialization</h3>
<pre>
<code>
// Closing the connection with the WebSocket
obj.stopAPI(APIsocket);
</code>
</pre>

<br />
<br />
<br />

<h3>Static effects</h3>
<pre>
<code>
obj.sendEffect(APIsocket, deviceType, effectType, scheme);
<br />
<br />
<b>PARAMETERS</b>
(<a href="https://assets.razerzone.com/dev_portal/websocket/html/md__websocket_external_03_keyboard.html">OFFICIAL RAZER REFERENCE</a>)
<br />
deviceType = 'keyboard'         (that's the only supported device at the time of writing)
effectType = 'CHROMA_STATIC'    (since we're making a static effect)
scheme = [                      (A 2-dimensional array that represents every LED on the keyboard) ( ! COLORS ARE BGR ! )
    [ 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 ],
    [ 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 ],
    [ 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 ],
    [ 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 ],
    [ 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 ],
    [ 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 ]
];
</code>
</pre>

<br />
<br />
<br />

<h3>Displaying text</h3>
<pre>
<code>
obj.displayText(APIsocket, AAlevel, delay, string, color);
<br />
<br />
<b>PARAMETERS</b>
<br />
(BETA) AAlevel = INT(1 - 256)                            (The level of anti-aliasing) (1 = OFF) ( ! 265 will be very CPU intensive and useless ! )
delay = INT(R)                                           (The delay between every shift on the keyboard)
string = STRING({YOUR TEXT})                             (The text you want to display on the keyboard)
color = INT(0 - 16777216) || INT(0x000000 - 0xffffff)    (The color in which you want the text to be displayed in) ( ! COLORS ARE BGR ! )
</code>
</pre>

<br />
<br />
<br />

<h3>Parsing INT_BGR-colors from CSS_HEX-colors</h3>
<pre>
<code>
obj.parseBGRIntFromCSS(color);
<br />
<br />
<b>PARAMETERS</b>
<br />
color = STRING('#000000' - '#ffffff')    (The CSS-color you want to parse into an integer)
</code>
</pre>
