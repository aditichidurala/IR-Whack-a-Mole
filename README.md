# IR-Whack-a-Mole
This is a Whack-a-Mole game designed and implemented on an Arduino using LEDs, an IR receiver, and an OLED display. The game features four "moles" represented by red and greed LEDs and includes remote pairing mode to map specific IR remote buttons to each mole. The score is tracked and show on OLED and game ends when all moles are red. 

# TinkerCad Model
<img width="1152" height="576" alt="image" src="https://github.com/user-attachments/assets/44188d44-3263-4dd9-abdd-0a9102ff6b3f" />
This is a TinkerCad Model of the Whack-a-Mole Game with Arduino, OLED, LEDs, and buttons all wired together. 

# State Machine Transitions
The Arduino program operates by dividing its tasks into three states, STATE_IDLE, STATE_REMOTE_SETPU, and STATE_GAME. There is a loop that runs indefinitely and the program utilizes the current state to decide what should happen. 

  The Arduino starts in the "STATE_IDLE" state where all the green LEDs are turned on (HIGH), all the red LEDs are turned off (LOW), and pushbuttons are configured to be pushed. The screen displays the "Whack a Mole / Press LEFT, for Setup / Press RIGHT to Start" message. 

  Pressing the Setup button changes the current state to "STATE_REMOTE_SETPU". This is where the program iterates through each mole index causing the matching green LED to blink until it detects the IR command sequence created by pressing a button on the remote. These buttons are saved to be used later in the game. Once all buttons are saved the system goes back to STATE_IDLE. 

  Pressing the Whack a Mole button changes current state to "STATE_GAME". This initiates the count down timer, clears game variables such as score, and resets all LEDs to red. After the countdown, the game starts and the moles randomly "pop up" by turning green until the corresponding button is pressed. If all LEDs turn red, the game is over and the system goes back to STATE_IDLE. 

# Actual Implementation
<img width="452" height="572" alt="image" src="https://github.com/user-attachments/assets/4fc1d618-9207-47a1-b52c-aa227471a4da" /> <img width="432" height="554" alt="image" src="https://github.com/user-attachments/assets/df0b5534-6f5c-481c-8b9f-e60b402382f5" />

Photos of all Moles in green/ red phases

# BOM
- 1 Arduino Uno
- 4 Green LEDs
- 4 Red LEDs
- 8 220 Ohm Resistors
- 2 10,000 Ohm Resistors
- 2 PushButtons
- 1 LCD 16 X 2 (I2C) Display
- 1 Large Breadboard
- 1 IR Receiver
- 1 IR Remote
- 22 Jumper Wires
