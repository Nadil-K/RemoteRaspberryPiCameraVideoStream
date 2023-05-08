# RemoteRaspberryPiCameraVideoStream
A python script to stream the video footage from Raspberry Pi Camera localy and broadcast over internet via remote.it

<h1>Instructions</h1>

Run following commands on Raspberry Pi terminal.

  1. sudo apt-get update
  2. sudo apt-get upgrade
  
Enable the Camera in Raspberry Pi configuration by following the given steps.

  Run sudo raspi-config on terminal.
  Go to: 3.Interface Options --> P1 Camera --> [Yes] --> [OK]
  Run sudo reboot on terminal

Wait till Raspberry Pi restarts.

Create a new .py file at /home/pi/ and name it. (RemoteRaspberyPiCameraStream.py)

Copy the python code provided here into the new .py created and save it.

Run 'ifconfig' on terminal and note down the ip address under wlan0.

Run the python script ("sudo python3 RemoteRaspberyPiCameraStream.py).

Open the web brower and visit "[ip address]:8000". If a live video stream is available, proceed forward, otherwise restart from the begining of the instructions.

Go to remote.it and create a new account. (If you do not have an account already)

Run "sudo apt install connectd" on terminal.

Run "sudo connectd_installer" and follow the steps given below.

Select 1 to log into the account by entering email and password.

Enter a name for the device.

Select 1 to attach a service.

Select 10. Custom (TCP) on the Protocol Selection Menu.

Enter a name for the service. (PiCamera)

Select 5 to exit.

Run "sudo nano /home/pi/.bashrc" on the terminal.

Go to the last line of the script and add:
    echo Running at boot 
    sudo python /home/pi/RemoteRaspberyPiCameraStream.py
    
Save and exit.

Reboot the Raspberry Pi.

Live stream will be available on remote.it

<h2>Access the Live Stream.</h2>

Log in to the Remote.it account from the device. Note that the device does not need to be on the same network as Raspberry Pi.

Select the device under the Devices tab.

Select the Service PiCamera which is online and press connect.

Copy the URL and paste it on the the browser. 

The live feed is up and it can be accessed from anywhere over any network.
