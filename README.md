# CameraSensors4Linux
Camera Sensors for linux using V4L2

Steps to follow : 

1.Should download and install VirtualBox extension pack which will supported USB 2.0 and USB 3.0 devices. 

    1.1 Launch “Oracle VirtualBox Manager” and navigate to “File” -> “Preferences”. 
    1-2. In ‘Preferences’ window, select ‘Extensions’.
    1-3. Press ‘Add new package’ icon.
    1-4. Select the extension pack and install it.

2.Restart both host and guest system.

    2.1 Go to Settings --> USB select USB 2.0 (EHCI) controller
    2.2 Look in Add new filters.
    Now your webcam appears in the list. Add those USB Filters. 

Incase if it does not appear try the following:

 Attaching webcam to guest OS
 
    2-1. Launch the guest OS.
    2-2. Launch “Command Prompt” on Windows  and go to VirtualBox folder.
         cd D:\orvirtualbox>
    2-3. List available cameras.
         D:\orvirtualbox>VBoxManage list webcams
    The result should be like below.
    Video Input Devices: 1
    .1 "Integrated Camera"
    \\?\usb#vid_5986&pid_2118&mi_00#6&491cadc&0&0000#{65e8773d-8f56-11d0-a3b9-00a0c9223196}\global
    2-4. Attach webcam(s) you want to use. The number at the end of the line specifies the camera. In this example, if you want       to   attach the front camera, type like this:
    VboxManage controlvm "Ubuntu 16.04.3" webcam attach .2
    *Replace “Ubuntu 16.04.3” with your guest OS name.
    *You can attach multiple cameras if you want.

3.Verify (Ubuntu Guest)

    3-1. Install it if it’s not already.  
         sudo apt-get install cheese
    3-2. Then, just type ‘cheese’ to launch. You should be able to see a video stream in newly opened ‘Cheese’ window.
         cheese

Thats It !!!
