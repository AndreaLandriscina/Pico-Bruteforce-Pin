# Bruteforce attack with Pico-Ducky
This project shows that through [Pico-Ducky](https://github.com/dbisu/pico-ducky) is possible to execute bruteforce attack on android devices. In order to do this, it has been necessary to use [Duckyscript 3.0](https://github.com/dbisu/pico-ducky/pull/125) and this was possible thanks to [Desperationis](https://github.com/Desperationis).
<br> <br> What is nice about this project in compare with similar is that it doesn't require root, adb, usb debugging and that the necessary hardware costs about 10 € (Pico-Ducky + OTG cable).

# Important information
Nowadays, bruteforce attacks on android devices are impossible due to the long time of wait between attempts (cooldown). However, certain phones may be vulnerable, especially the old ones. In addition, there are some list of PIN that increse the probability of unlocking, since some PIN are more likely to be used than others.
A list of supported and unsoppurted phones, besides a lot of other useful information, is available on [Android-PIN-Bruteforce](https://github.com/urbanadventurer/Android-PIN-Bruteforce/tree/master).

# Payload
- Payload0 injects every possible PIN from 0000 to 9999. The WAIT function must be modified based on the lockscreen of the phone, in particolar based on the time of wait and the number of possible attempts between the cooldown.
- Payload1 injects the most frequently used PIN.

An important problem is how to notice when the phone gets unlocked, because if this gets locked again we won't know the phone has been unlocked. In order to discover the PIN, at each PIN inserted, the payload will try to make a request on a server that you have to own. The best way that i found is to use XAMPP and No-IP. In this way, after N attempts, we could check if a request has been made and in the positive case the phone has been unlocked.
