# 5. External System Integration

> Flasheye collaborates and integrate with other world leading platforms and user interfaces for alarms, management and control. This allows you to continue to work with existing platforms and infrastructure, and integrate your LiDAR sensors to enhance the overall performance. 

## Milestone
Flasheye security solution is integrated with Milestone video management system for surveillance operation. Partners and customers can integrate Flasheye security system with Milestone and use Milestone’s product suite and solutions for operation, monitoring, presentation and configuration of the Flasheye’s applications. Milestone Systems is one of the leading providers of open platform video management software.

![Milestone Logo](../_media/esi_pic1_logo.png)

## MQTT
Flasheye Security solution delivers sensor data and sensor intelligence for real-time alerts, point-cloud data etc. through a well-defined interface, based on MQTT. The MQTT topics and messages are specified by Flasheye and the MQTT API is secured and supports MQTT over TLS, authentication mechanisms, tokens and encryption. 

MQTT is a publish-subscribe based messaging protocol, very simple and lightweight. It is an application layer protocol that works on top of the TCP/IP stack. MQTT has a client server model where every Flasheye LPU or server are a client which connects to a server, i.e., the MQTT broker. The Flasheye LPU or server will connect to the broker and publish data to a topic. A subscriber will receive the message published by a client if it is subscribed to that topic.
