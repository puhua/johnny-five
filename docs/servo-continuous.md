# Servo Continuous

Run with:
```bash
node eg/servo-continuous.js
```


```javascript
var five = require("johnny-five"),
  board, servo;

board = new five.Board();

board.on("ready", function() {

  // Create a new `servo` hardware instance.
  servo = new five.Servo({
    pin: 10,
    // `type` defaults to standard servo.
    // For continuous rotation servos, override the default
    // by setting the `type` here
    type: "continuous"
  });

  // Inject the `servo` hardware into
  // the Repl instance's context;
  // allows direct command line access
  board.repl.inject({
    servo: servo
  });

  // Continuous Rotation Servo API

  // cw( speed )
  // clockWise( speed)
  // ccw( speed )
  // counterClockwise( speed )
  //
  // Set the speed at which the continuous rotation
  // servo will rotate at, either clockwise or counter
  // clockwise, respectively
  servo.cw(0.5); // half speed clockwise

});

```


## Breadboard/Illustration


![docs/breadboard/servo-continuous.png](breadboard/servo-continuous.png)
[docs/breadboard/servo-continuous.fzz](breadboard/servo-continuous.fzz)





## License
Copyright (c) 2012, 2013, 2014 Rick Waldron <waldron.rick@gmail.com>
Licensed under the MIT license.
Copyright (c) 2014, 2015 The Johnny-Five Contributors
Licensed under the MIT license.
