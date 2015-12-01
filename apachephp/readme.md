##todo

SMS URL in synology sms screen:
http://(ip of the nas>:<port you forwarded to port 80)/?broker=(yourbrokerip)&sender=(nameofthesener)&topic=synology/1&payload=hello+world&phone=123456789&user=foo&password=bar


##brainfart
adding a mqttbroker wich will bridge to the other mqttbroker and queues the messages when the target broker is down.
