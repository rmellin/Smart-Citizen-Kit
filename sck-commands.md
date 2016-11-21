## SCK Serial Commands

The Smart Citizen Kit can be managed over a basic serial protocol. You just need the **Arduino IDE Serial Monitor** or any other **Serial Utility** like **Screen** in order to use it.

#### How to use it.

* Connect to your kit using any serial utility, any baud-rate should work but `115200` is recommendable.
* Send the starting commands.
* Notice all the commands except the starting commands require a carriage return at the end: `CR` or `\r`  .
* Call any command you want, change `XXX` with the corresponding value.

### Basic SCK setup commands

This commands are commands to talk directly to the Wi-Fi module (RN-XV WiFly) own interface.

* `$$$`							Wake up the module and enter WiFly commands mode
* `set wlan ssid XXX\r`        Add a new SSID to memory
* `set wlan phrase XXX\r`      Add a new phrase to memory
* `set wlan key XXX\r`         Add a new key to memory
* `set wlan auth XXX\r`        Add an authentication method into memory
* `set wlan ext_antenna XXX\r` Add an antenna type into memory
* `set sys iofunc 0x7`         Disable the Wi-Fi module blue LED's 
* `exit\r`                     Go back to normal operational mode

### Special SCK commands

This commands are commands to talk talk to the SCK configuration interface.

* `###`							Wake up the module and enter SCK commands mode
* `get mac\r`                  Get the MAC address of the kit
* `get time update\r`          Retrieve the sensor update interval
* `set time update XXX\r`    	Update the sensor update interval
* `get number updates\r`    	Retrieve the max number of bulk updates allowed
* `set number updates XXX\r`   Update the max number of bulk updates allowed
* `get apikey\r`               Retrieve the kit APIKEY
* `set apikey XXX\r`           Update the kit APIKEY
* `get wlan ssid\r`            Retrieve the SSID saved on the kit
* `get wlan phrase\r`          Retrieve the phrase and KEY saved on the kit
* `get wlan auth\r`            Retrieve the authentication methods saved on the kit
* `get wlan ext_antenna\r`     Retrieve the antenna types saved on the kit
* `get all\r`                  Retrieve all config saved on the kit in a single line (`|version|MAC|ssid1 ssid2,pass1 pass2,auth1 auth2,ant1 ant2|hardcodedNets|timeUpdate|numPosts|`)
* `post data\r`                Retrieve sensor readings and post them to server if network connection is available.
* `clear nets\r`               Remove all saved Wi-Fi configuration information (except hardcoded)
* `clear memory\r`             Remove all configuration information
* `exit\r`                     Goes back to normal operational mode
* `#data\r`  					Retrieves sensor readings stored in memory
