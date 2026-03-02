TEAM- VISHNU
 SOLUTION FOR PROBLEM STATEMENT:
1. The Lightweight Hardware Stack:

Brain: NVIDIA Jetson Orin Nano (80g) or Raspberry Pi 5 (46g). This runs the AI model (YOLO or MobileNet) to count people from the camera feed.
Satellite Modem: Swarm M138 Modem (9.6g). This is the "breakthrough" for small drones. It is about the size of a credit card and can send short text messages (metadata) to the Swarm/SpaceX satellite constellation.
Antenna: VHF Antenna (approx. 20g). Required to talk to the satellites.

2. How the "Data-Only" Transmission Works:

Since you aren't sending video, you only need to transmit a few bytes of text. The communication flow looks like this:
Local Inference: The drone flies over the disaster zone. The camera sees a group. The onboard AI says: "I see 12 people."
Packet Creation: The processor creates a tiny data packet: {"count": 12, "lat": 17.38, "lon": 78.48}.
Satellite Uplink: The Swarm M138 sends this message to a passing satellite. Because the message is so small, it transmits in a fraction of a second.
Base Station Alert: The satellite beams that message back down to the nearest ground station, which then sends it to your phone or laptop as a text alert or a pin on a map.
