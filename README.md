#JogDial.js#

##A JavaScript plugin for jog dial controls.##
JogDial is a simple JavaScript plugin that help you to create dial style controller easily on the webpage.

##Supported browsers and device##
JogDial supports Chrome, Safari, FireFox, Internet Explorer 7+ and most of modern browsers include mobile device.

##Features##
* Does not require any other JavaScript library like jQuery.
* Cross-browser support (IE7+)
* Multi-touch support (you can control multiple number of JogDial elements at once in touch screen) 
* DOM Events
* AMD Support (RequreJS)

##Demo###
[Click here](http://www.ohsean.net/plugins/jogdial/)

##Usage##

###Basics###
Here is a basic example of JogDial.js initialization. This will start the JogDial in debug mode.

You must create the target element for the JogDial and setup the width and height property before the code start.

    var el = document.getElementById('your_element');
    var dial = JogDial(el, {debug: true});
    
You can change the setting by passing an options (`array`) in second argument.

    var options = {debug: true, wheelSize: 90%, knobSize: 50%, minDegree: 0};
    var dial = JogDial(el, options);
    
###Styling###
The easiest way to style the JogDial is adding background image to your target element and knob element created from JogDial script.

JodDial always return the knob id name append to the target element name you've created.

For an example, if you named the tag element id as __"dial"__, then knob id will be __"dial_knob"__.

    #dial {
        width: 200px;
        height: 200px;
    }
    
    #dial_knob {
        // This is your knob style
    }
    
You can add any additional elements inside of your target element and it won't interfere the JogDial function.


###Options###
Here is a list of options can be used on JogDial.

Options              | Descriptions                                                     | Default         
:------------------- |:-----------------------------------------------------------------|:---------------
debug `bool`         | Show debug overlay on the top of screen                          |false           |
touchMode `string`   | Set the active touch area of JogDial control. 'knob' or 'wheel'  |knob            |
knobSize `int`       | Set the diameter of knob in percentage or pixel                  |30%             |
wheelSize `int`      | Set the diameter of wheel in percentage or pixel                 |100%            |
zIndex `int`         | Set the z-index of JogDial                                       |9999            |
degreeStartAt `int`  | Set the degree of wheel at start                                 |0               |
minDegree `int`      | Set the minimum degree of wheel rotation                         |null (infinite) |
maxDegree `int`      | Set the maximum degree of wheel rotation                         |null (infinite) |

###Events###
Events can be added or removed with the on and off methods and those are chainable like a jQuery.
    
    JogDial(el, {debug: true})
    .on("mousemove", function(event){ console.log(event.target.rotation); })
    .on("mouseup", function(event){ console.log(event.target.rotation); });

####Event list####
* mousedown
* mousemove
* mouseup

####Event Data list from callback####
    event.target.rotation  {number}     total sum of rotated degree from the start.
    event.target.degree    {number}     Current degree of circle in clock angle.
    
####Triggering####
You can change the angle of JogDial element by passing the number value to 'angle' function.

    var dial = JogDial(el, {debug: true});
    dial.angle(45); 
    // This will change the JogDial degree to 45.
    
    
##Copyrights##
Licensed under the MIT license 