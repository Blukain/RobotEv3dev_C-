# RobotEv3dev_C-
Repo C++ based on Ev3dev

## Intro
This repository is about how to setup your system on linux for developing on Ev3dev with C++.

This little guide will set you up and running, is based on ev3dev-jessie firmware and its C++ library made by Denis Demidov,
that can be found at [DDemidov](https://github.com/ddemidov/ev3dev-lang-cpp) repository.

I have corrected some problems regarding Ports for motors and Cmake file to let it compile straight from the project with out any problem.
Experiment yourself.

### Basics before starting
Once you have your linux system ready, first of all you might start from installing needed basic software and IDE, 
I personally prefer to use JetBrains CLion when C or C++ comes in, in my opinion is a good IDE to start.

To start let install via apt "cmake", "gcc-arm-linux-gnueabi", "g++-arm-linux-gnueabi" and finally "g++", these are the needed packages to start code and compile 
your Ev3dev C++ project.

Keep in mind that usally linux come with only gcc compiler installed and Clion and make require g++ too in order to get a perfect setup.

### Setup a connection USB with Ev3dev
Once everthing is installed, you should configure a ethernet connection in order to ssh onto the robot or upload files.
1. Check network connection panel and look for connection that has on ethernet tab - device: enx121653xxxxxx this should be ev3 proprietary macAddress.
2. Change device to enx121653xxxxxx (12:16:53:xx:xx:xx) and under ipv4 set method: shared to others.
3. Open up a terminal and use ssh: "ssh robot@ev3dev.local", answer yes on key security, and when asked password use "maker".
4. Thats it you are into Ev3dev on ssh!

### Upload compiled file to Ev3dev
Before starting to upload a compiled file you might put your project into Clion project folder or another folder it doesnt matter but to make it simpler we will use Clion one.
In this case just copy extracted folder ev3dev-lang-cpp-jessie into CLion project folder and thats all. Once you open up the project in Clion after build is done with no errors you can proceed with its upload.

To upload a file into the robot just go at bottom of Clion on terminal tab, go to this folder: ~/CLionProjects/ev3dev-lang-cpp-jessie/cmake-build-debug, where your exe file will be generated, and just type: "scp filename robot@ev3dev.local:/home/robot", insert your password and you will be done.

Now start your program on ev3 and enjoy!
