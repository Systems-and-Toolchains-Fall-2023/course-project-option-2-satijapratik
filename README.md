[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/yDpbj8_M)
##############################################################################################################

About the project:

In this project, we are taking the MQTT dataset from Kaggle and integrating it in to a Postgress table. We then used python to do some intial analysis on the table via Pyspark and do preprocessing to prepar the data for use in a machine learning model. We will build two seperate models to analyze the data, one using Pyspark and one using TensorFlow. The models will have different classifiers and regressors, which will each be tuned and then the best model will be chosen. Finally, we will run the models in the cloud using Google Cloud Compute and create a final report on the results.
##############################################################################################################

About the dataset:

"The [MQTT data set] is related to a smart home environment where sensors retrieve information about temperature, light, humidity, CO-Gas, motion, smoke, door and fan with different time interval since the behaviour of each sensor is different with the others."

This dataset was chosen for its applications to the real world, where information from various sensors or inputs will need to be interpreted to gleam some insight not readily available to the human eye.

The dataset itself along with more information can be found at https://www.kaggle.com/datasets/cnrieiit/mqttset/.

##############################################################################################################
# Column                   |Contraints and type   | Description                                              # 
##############################################################################################################
tcp_flags                  |not nullable, hex     | TCP flags
tcp_time_delta             |not nullable          | Time difference between two TCP packets
tcp_len                    |not nullable, int     | Length of TCP packets
mqtt_conack_flags          |nullable="0", hex     | MQTT Flags
mqtt_conack_flags_reserved |not nullable, double  | Reserved MQTT Flag
mqtt_conack_flags_sp       |not nullable, double  | Another MQTT Flag
mqtt_conack_val            |double, 0-158         | Indicates the result of the connection attempt between a client and a broker
mqtt_conflag_cleansess     |not nullable          | MQTT clean flag
mqtt_conflag_passwd        |not nullable          | MQTT password presence
mqtt_conflag_qos           |not nullable          | Quality of service level
mqtt_conflag_reserved      |not nullable          | Resevered Flag
mqtt_conflag_retain        |not nullable          | Whether message should be reserved 
mqtt_conflag_uname         |not nullable          | Username present or not
mqtt_conflag_willflag      |not nullable          | Last will message flag
mqtt_conflags              |nullable="0", hex     | Indicates whether the client requests a clean session or a persistent session with the broker.
mqtt_dupflag               |not nullable, binary  | Indicates that a message is a duplicate and has been resent because the intended recipient did not ack
mqtt_hdrflags              |nullable="0", hex     | The first byte of the fixed header in the MQTT packet
mqtt_kalive                |double                | Kepp-alive interval used for MQTT connections
mqtt_len                   |not nullable, int     | Length of MQTT packets
mqtt_msg                   |not nullable, double  | MQTT messages
mqtt_msgid                 |not nullable          | MQTT message ID 
mqtt_msgtype               |not nullable, int 0-14| Type of MQTT message 
mqtt_proto_len             |not nullable, double  | Length related to MQTT protocol
mqtt_protoname             |nullable="0", "MQTT"  | Name of MQTT protocol
mqtt_qos                   |not nullable, double  | Quality of service for MQTT
mqtt_retain                |not nullable, double  | Retain flag for MQTT
mqtt_sub_qos               |not nullable, double  | Quality of Service level for MQTT subscription
mqtt_suback_qos            |not nullable, double  | Quality of Service level in MQTT subscription acknowledgments
mqtt_ver                   |not nullable, double  | MQTT protocol version
mqtt_willmsg               |not nullable, double  | The "last will" message in MQTT
mqtt_willmsg_len           |not nullable, double  | Length of the MQTT "last will" message
mqtt_willtopic             |not nullable, double  | MQTT "last will" topic
mqtt_willtopic_len         |not nullable, double  | Length of the MQTT "last will" topic
target                     |legitimate/dos/malformed/slowite/bruteforce/Flooding, not nullable, string | Attack or not, if attack then what kind
train                      |int, not nullable     | Test (0) or Train (1) dataset
##############################################################################################################

About the models:

Pyspark ML:
1 - The first model chosen was a Linear Regression using the pyspark ML package. The model was tuned using regParam and maxIter, or the learning 
    rate and the maximum number of epochs run before stopping. 
    The testing accuracy after hyperparameter tuning was ____%

2 - The second model run through the pyspark ML package was a Random Forest Decision Tree. This model was tuned using maxDepth and numTrees as
    hyperparameters, which are paremters representing the maximum depth any given tree can go and how many trees are averaged for the final 
    random forest. 
    The testing accuracy after hyperparameter tuning was ____%

Pytorch:
1 - The first pytorch model trained was a deep neural network, with 4 hidden layers and 128 neurons in each layer. The activation function chosen
    was RReLU, the loss function was cross entropy, and the adam optimizer was picked. The final learning rate chosen was 0.005 with a decay rate of
    0.995. 
    The testing accuracy after hyperparameter tuning was ____%

2 - The second pytorch model trained was a shallowe neural network, with 2 hidden layers of 8 neurons each. The activation function chosen this time 
    was ReLU, the loss function and optimizer remained the same. The final learning rate chosen was 0.05 with no decay rate. 
    The testing accuracy after hyperparameter tuning was ____%