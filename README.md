# Aquila Gateway

MQTT-SN gateway for Aquila 2.0 platform.

## Supported MQTT-SN features

- QoS: supports QoS0, QoS1 and QoS2 (QoS2 implementation is mostly dummy, equivalent to QoS1)
- Commands:
  - ADVERTISE
  - CONNECT
  - CONNACK
  - DISCONNECT
  - WILLTOPICREQ
  - WILLTOPIC
  - WILLMSGREQ
  - WILLMSG
  - REGISTER
  - REGACK
  - PUBLISH
  - PUBACK
  - SUBSCRIBE
  - SUBACK
  - UNSUBSCRIBE
  - UNSUBACK
  - PINGREQ
  - PINGRESP
  - WILLTOPICUPD
  - WILLMSGUPD
  - WILLTOPICRESP
  - WILLMSGRESP
  - PUBREC, PUBREL, PBCOMP (QoS2)
  - SEARCHGW (basic, not spec checked)
  - GWINFO (basic, not spec checked)
- Implements Forwarder Encapsulation spec with a little modification: adds lqi and rssi data at the start of the frame.
- Supports topic register
- Supports last will
- Supports and manages disconnect timeout
- Will update
- Subscribe, Unsubscribe
- Retained messages support (issue: when a device subscribes to a topic with a retained message, it will be resent to all devices susbscribed to it, check if it's a problem)

## TODO

- QoS -1
- WILDCARDS
- Sleeping nodes -> message buffering
- Short and predefined MQTT-SN topics


## TODO Mid-term

- Support other transports: TCP socket (for using an ESPino or similar as forwarder)
- Advanced device management: implement predefined Gateway topics for getting info of connected devices, events etc. (non MQTT-SN standard, implement as module)
- Device pairing management

## TOTEST

- Removing subscriptions
- Check disconect parser, should accept messages without duration field
- Check if parser on willtopicupd accept empty flags and topic (for removing will)
- Will update