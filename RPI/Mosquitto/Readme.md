Installation1.: Open a new terminal window

2.: Update the system with:pi@raspberry:~ $ sudo apt update3.: Install Mosquitto with:pi@raspberry:~ $ sudo apt install -y mosquitto4.: Install Clients:pi@raspberry:~ $ sudo apt install -y mosquitto-clients

To enable auto-start on system boot type:pi@raspberry:~ $ sudo systemctl enable mosquitto.service

Test Installation

To test the installation open a second terminal window. From the first terminal subsribe to the “test” topic with the mosquitto_sub command:pi@raspberry:~ $ mosquitto_sub -h localhost -t test From the second terminal publish a “Hello World” message to the test topic with the mosquitto_pub:pi@raspberry:~ $ mosquitto_pub -h localhost -t test -m “hello world” When you hit enter you should see the Hello World message pop up in the first terminal window. Congratulations! You just send your first message ?

SSL CONFIGURATION

let mosquitto server use the modified configuration file (you can find it in the same folder here). Also we need to place the credintils in the /etc/mosquitto/ folders based on the configuration file

mosquitto -c /etc/mosquitto/mosquitto.conf -d &

exit




