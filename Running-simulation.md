---
description: Guide to run simulation setup for NXP AIM CHALLENGE.
---

# Running of AIM 2024 software stack

To run the simulation, run the following commands in a new Terminal Window

```
$ ros2 launch b3rb_gz_bringup sil.launch.py world:=Raceway_1
```

Running this will launch the gazebo simulation and Xterm window as follows:

![](.gitbook/assets/AIM_2024/sample_world_0.png)

![](.gitbook/assets/AIM_2024/sample_world_1.png)

![](.gitbook/assets/AIM_2024/sample_world_2.png)

On a different terminal run the following code:

```
$ source ~/cognipilot/cranium/install/setup.bash
$ ros2 run b3rb_ros_line_follower vectors
```

On a different terminal run the following code:

```
$ source ~/cognipilot/cranium/install/setup.bash
$ ros2 run b3rb_ros_line_follower runner
```

On a different terminal run the following code:

```
$ source ~/cognipilot/cranium/install/setup.bash
$ ros2 run b3rb_ros_line_follower detect
```

_**Running the above 3 commands should make the buggy move autonomously now in simulation.**_

{% hint style="danger" %}
If on execution of any \__ros2 run b3rb\_ros\_line\_follower_ gives error like below, it means that sourcing of setup.bash was unsuccesful
{% endhint %}

![](.gitbook/assets/AIM_S2/line_follower_fail.png)

## Troubleshooting

If after successful installation done on step-6, one is still facing issue on executing ros2 run b3rb\_ros\_line\_follower vectors/detect/runner commands, then please make sure that the packaage installed in /cognipilot/cranium/src for br3b\_ros\_line\_follower is same as this folder: https://github.com/NXPHoverGames/NXP\_AIM\_INDIA\_2024/tree/main/b3rb\_ros\_line\_follower

There seems issue from github side, where it is clonning previous unstable commit files and will cause issue. Please repalce the content with the content available on github and re-build the setup and try running again.

If issue is still not resolved try this approach: Please clone the setup from https://github.com/NXPHoverGames/NXP\_AIM\_INDIA\_2024/tree/main and manually follow steps given here: https://github.com/NXPHoverGames/NXP\_AIM\_INDIA\_2024/tree/main?tab=readme-ov-file#execution-steps
