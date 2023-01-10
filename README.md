# Humanoid Robot Wrestling Controller Example

[![webots.cloud - Competition](https://img.shields.io/badge/webots.cloud-Competition-007ACC)][1]

## Alice controller

Minimalist controller example for the Robot Wrestling Tournament.
Demonstrates how to play a simple motion file. We use the [Motion class](https://cyberbotics.com/doc/reference/motion?tab-language=python) from Webots.

``` Python
from controller import Robot, Motion


class Alice (Robot):
    def run(self):
        # motion files are text files containing pre-recorded positions of the robot's joints
        handWave = Motion('../motions/HandWave.motion')  # look into this text file, it's easy to understand
        handWave.setLoop(True)
        handWave.play()
        time_step = int(self.getBasicTimeStep())  # retrieves the simulation time step (ms) from the world file
        while self.step(time_step) != -1:  # Mandatory function to make the simulation run
            pass


# create the Robot instance and run main loop
wrestler = Alice()
wrestler.run()
```

[Bob](https://github.com/cyberbotics/wrestling-bob) is a more advanced robot controller able to win against Alice.

[1]: https://webots.cloud/run?version=R2022b&url=https%3A%2F%2Fgithub.com%2Fcyberbotics%2Fwrestling%2Fblob%2Fmain%2Fworlds%2Fwrestling.wbt&type=competition "Leaderboard"
