# Evaluation Platform For Grand Finale

{% hint style="danger" %}
Participanting teams that are will do the following changes will automatically be eliminated from the competition.
{% endhint %}

* For the evaluation of NXP AIM 2024 Grand Finale, following are the requirements from the participants -
  * **REQUIREMENTS (TO BE PERFORMED ON THE NAVQPLUS)** Ensure the ROS2 version is HUMBLE. (Command for checking: "echo $ROS\_DISTRO".)
    * Ensure the ROS2 version is HUMBLE. (Command for checking: "echo $ROS\_DISTRO".)
    * NavQPlus must have the following ROS2 environment variables configuration:
      * ROS\_DOMAIN\_ID=7
      * ROS\_LOCALHOST\_ONLY=0
      * (Note: Commands for these are added in "\~/.bashrc" when setting up CogniPilot.)
    * You may refer "[github.com/NXPHoverGames/b3rb\_robot/tree/nxp\_aim\_2024\_pose\_eval](https://github.com/NXPHoverGames/b3rb_robot/commit/829d95daa83af8a5701eb255d916b52481d89fd6)" for the following:
      * In the file "\~/cognipilot/cranium/src/b3rb\_robot/b3rb\_bringup/launch/robot.launch.py", at line = 167:
        * Comment the following nodes from the LaunchDescription object returned in robot.launch.py:
          * nav2, corti, slam, localization.
      * In the file "\~/cognipilot/cranium/src/b3rb\_robot/b3rb\_bringup/launch/laser.launch.py", at line = 50:
        * Set pub\_rate as 4.0.
    * Comment the following lines in the "\~/.bashrc" at NavQ+.
      * export RMW\_IMPLEMENTATION=rmw\_cyclonedds\_cpp
      * export CYCLONEDDS\_URI=/home/$USER/CycloneDDSConfig.xml
      * (Then, restart NavQPlus.)

{% hint style="info" %}
After above steps make sure to re-build using colcon build followed by source.
{% endhint %}

{% hint style="danger" %}
Participants should not change cranium nodes other than the ones in \~/cognipilot/cranium/src/b3rb\_ros\_line\_follower and \~/cognipilot/cranium/src/synapse\_msgs.
{% endhint %}
