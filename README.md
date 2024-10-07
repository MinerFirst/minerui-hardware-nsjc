NSJC is a Linux daemon which uses the evdev devices provided by Hid-Nintendo (formerly known as Hid-Joycon) to implement Joy-Con pairing.

Hid-Nintendo is currently in review on the Linux-input mailing list. The most recent patches are currently found at https://github.com/DanielOgorchock/linux

# Installation
1. Clone the repo
2. Install requirements (`sudo apt install libevdev-dev` or `sudo dnf install libevdev-devel libudev-devel`)
3. `cmake .`
4. `sudo make install`
5. `sudo systemctl enable --now joycond`

# Usage
When a Joy-Con or pro controller is connected via bluetooth or USB, the player LED's should start blinking periodically. This signals that the controller is in pairing mode.

For the pro controller, pressing both triggers will "pair" it.

For the pro controller, pressing Plus and Minus will pair it as a virtual controller.
This is useful when using Steam.

With the Joy-Cons, to use a single contoller alone, hold ZL and L at the same time (ZR and R for the right joy-con). Alternatively, hold both S triggers at once.

To combine two joy-cons into a virtual input device, press a *single* trigger on both of them at the same time. A new uinput device will be created called "Nintendo Switch Combined Joy-Cons".

Rumble support is now functional for the combined Joy-Con uinput device.
