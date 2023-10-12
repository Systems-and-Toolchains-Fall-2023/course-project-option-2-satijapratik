[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/yDpbj8_M)
##############################################################################################################
# Column                   |Contraints and type | Description                                                # 
##############################################################################################################
tcp_flags                  |not nullable, hex   | TCP flags
tcp_time_delta             |not nullable        | Time difference between two TCP packets
tcp_len                    |not nullable, int   | Length of TCP packets
mqtt_conack_flags          |nullable="0", hex   | MQTT Flags
mqtt_conack_flags_reserved |not nullable, double| Reserved MQTT Flag
mqtt_conack_flags_sp       |not nullable, double| Another MQTT Flag
mqtt_conack_val            |double, 0-158       | Indicates the result of the connection attempt between a client and a broker
mqtt_conflag_cleansess     |not nullable        | MQTT clean flag
mqtt_conflag_passwd        |not nullable        | MQTT password presence
mqtt_conflag_qos           |not nullable        | Quality of service level
mqtt_conflag_reserved      |not nullable        | Resevered Flag
mqtt_conflag_retain        |not nullable        | Whether message should be reserved 
mqtt_conflag_uname         |not nullable        | Username present or not
mqtt_conflag_willflag      |not nullable        | Last will message flag
mqtt_conflags              |nullable="0", hex   | Indicates whether the client requests a clean session or a persistent session with the broker.
mqtt_dupflag               |not nullable, binary| Indicates that a message is a duplicate and has been resent because the intended recipient did not ack
mqtt_hdrflags              |nullable="0", hex   | The first byte of the fixed header in the MQTT packet
mqtt_kalive                |double              | Kepp-alive interval used for MQTT connections
mqtt_len                   |not nullable, int   | Length of MQTT packets
mqtt_msg                   |not nullable, double| MQTT messages
mqtt_msgid                 |not nullable        | MQTT message ID 
mqtt_msgtype               |notnullable,int 0-14| Type of MQTT message 
mqtt_proto_len             |not nullable, double| Length related to MQTT protocol
mqtt_protoname             |nullable="0", "MQTT"| Name of MQTT protocol
mqtt_qos                   |not nullable, double| Quality of service for MQTT
mqtt_retain                |not nullable, double| Retain flag for MQTT
mqtt_sub_qos               |not nullable, double| Quality of Service level for MQTT subscription
mqtt_suback_qos            |not nullable, double| Quality of Service level in MQTT subscription acknowledgments
mqtt_ver                   |not nullable, double| MQTT protocol version
mqtt_willmsg               |not nullable, double| The "last will" message in MQTT
mqtt_willmsg_len           |not nullable, double| Length of the MQTT "last will" message
mqtt_willtopic             |not nullable, double| MQTT "last will" topic
mqtt_willtopic_len         |not nullable, double| Length of the MQTT "last will" topic
target                     |legitimate/dos/malformed/slowite/bruteforce, not nullable, string | Attack or not, if attack then what kind
train                      |int, not nullable   | Test (0) or Train (1) dataset