# Exploring MQTT QoS Levels

Experiment with QoS 0, 1, and 2.
Observe how message delivery changes based on QoS settings.

## Publisher_qos.py output

```
  client = mqtt.Client()
[16:11:00] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
Enter message to publish: [16:11:00] DEBUG | Received CONNACK (0, 0)
Hello World!!!!!!!!11
Enter QoS level (0, 1, 2): 2
[16:11:10] DEBUG | Sending PUBLISH (d0, q2, r0, m1), 'b'test/qos/6510301004/temperature'', ... (21 bytes)
[16:11:10] PUBLISH REQUESTED | QoS=2 | Message='Hello World!!!!!!!!11' | msgid=1
Enter message to publish: [16:11:10] DEBUG | Received PUBREC (Mid: 1)
[16:11:10] DEBUG | Sending PUBREL (Mid: 1)
[16:11:10] DEBUG | Received PUBCOMP (Mid: 1)
[16:11:10] PUBLISHED | msgid=1
[16:12:01] DEBUG | Sending PINGREQ
[16:12:01] DEBUG | Received PINGRESP
```

## Subscriber_qos.py Output

```
  client = mqtt.Client()
[16:10:29] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
[16:10:29] DEBUG | Received CONNACK (0, 0)
[16:10:29] Connected with result code 0
[16:10:29] DEBUG | Sending SUBSCRIBE (d0, m1) [(b'test/qos/6510301004', 2)]
[16:10:29] DEBUG | Received SUBACK
```