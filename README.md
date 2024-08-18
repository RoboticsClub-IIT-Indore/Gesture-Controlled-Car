# Gesture-Controlled Car
This project utilizes mediapipe library to get landmark points of hand and using simple distance calculations between the coordinates to compute different hand gestures. Communication between ESP8266 and the running python script(to identify gestures) is performed via being on the same Wi-Fi network. These hand gestures are then sent to ESP8266 which is then responsible for turning the wheels accordingly to move forward, sideways, etc. The wheels used here are mecanum wheels which are a special type of wheels which can be used to move the car into a circle or move them sideways.

## Code walkthrough
- `ip_address.ino` file can be used to find the IP address of ESP8266 on the Wi-Fi network in case we aren't aware of it.
- `transmitter.py` file figures out the hand gestures and sends them to ESP8266.
- `esp_8266_receiver.ino` is the file which is uploaded onto ESP8266 which performs actions based on the gestures identified by the python script.

## Dependencies
1. **NodeMCU ESP8266 Driver:** this will be required when you try to upload the code onto the micro-controller.
2. **Python libraries:** to run the `transmitter.py` script you will be required to install the following libraries:
  - Mediapipe
  - Socket
  - OpenCV

## Steps to run the setup
1. Replace the IP address in `esp_8266_receiver.ino` file and Wi-Fi network ID and password in `transmitter.py` file.
2. Upload `esp_8266_receiver.ino` onto the micro-controller via Arduino software.
3. Start `transmitter.py` script and wait until it says in the terminal "Connected to server". This will mean connections to the server are fine.
4. You can now check to see if the gestures are being detected well. You can also connect the micro-controller to your PC to check if serial monitor is printing the correct gestures.
