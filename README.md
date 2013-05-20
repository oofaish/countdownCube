countdownCube
=============

countdown cube is a jQuery plugin that is in form of a bunch of rotating 3d cubes. You can see an example in http://cigari.co.uk/countdown

make sure you ahve jQuery loaded - link the following files:

    <link rel="stylesheet" href="countdownCube.css"/>
    <script type="text/javascript" src="countdowncube.js"></script>

add a new empty div to your page:

    <div id="counter"></div>

adn then kick off a new counter, with a targert time, and if you like size (in pixels), background (color), and font Color:

    $('#counter').countdownCube( {
      target: new Date( 'April 26, 2014 13:30:00' ),
      cubeSize: 50,
      background: 'rgba( 255, 150, 150, 0.8 )',
      color: 'white',
      } );

You can have more than one countdownCube per page.

I have only tested it on latest Chrome, Firefox and Safari.

Feel free to use it as it wish, but I would appreciate a plug to my website http://cigari.co.uk

The MIT License (MIT)

Copyright (c) 2013 Ali Cigari @oofaish

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
