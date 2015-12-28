countdownCube
=============

CountdownCube is a jQuery plugin that is in the form of a bunch of rotating 3D cubes. You can see an example in http://www.cigari.co.uk/countdown

It uses CSS transitions to create the 3D rotating cube effects.

Make sure you have jQuery loaded - link the following files:

    <link rel="stylesheet" href="countdownCube.css"/>
    <script type="text/javascript" src="countdowncube.js"></script>

Add a new empty div to your page:

    <div id="counter"></div>

And then kick off a new counter, with a target time, and if you like cubeSize (in pixels), background color, and font color:

    $('#counter').countdownCube( {
      target: new Date( 'April 26, 2014 13:30:00' ),
      cubeSize: 50,
      background: 'rgba( 255, 150, 150, 0.8 )',
      color: 'white',
      } );

You can have more than one countdownCube per page.

I have only tested it on latest Chrome, Firefox and Safari.

Feel free to use it as it wish, but I would appreciate a plug to my website http://www.cigari.co.uk

Copyright (c) 2013 Ali Cigari @oofaish
