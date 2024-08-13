### MQTT Protocol
MQTT is designed for constrained devices and low-bandwidth, high-latency, or unreliable networks. It is optimized for real-time data exchange with minimal overhead.

### Core Concepts of MQTT
1. **Publish-Subscribe Model**
   * Publishers: Device that sends data to the network. A publisher does not need to know the recipient of data.
   * Subscribers: Device which receive the data. A subscriber subscribes to a specific topic and receives all messages publish on this topic.
   * Broker: The central server that receive all messages from publishers and routes them to the correct subscribers.

   **Advantage**
   * Decouple the producers and consumers of data.
   * Supports one-to-many and many-to-one communication.

2. **Topics**
   * Hierarchical Naming system: Messages are sent to "topics" which are string that act like channels. Topics can be hierarchical, using a slash to create a structure
   * Wildcard subscription: Subscribers can use wildcards to subscribe multiple topics with a single subscription. For example `home/+/temperature`subscribes to temperature updates from any room.

   **Example**
   * A temperature sensor publishes data to the topic `home/livingroom/temperature`.
   * A subscriber interested i living room temperature data subscribe to `home/livingroom/temperature`.

3. **QOS (Quality of Service) Levels**
   * MQTT provides three QOS levels to balance between message delivery guarantees and network efficiency:
     * **QOS 0 - At most once :** the message is delivered at least once, with no acknowledgment, and no retries if the message is lost. Suitable for non-critical data where occasional loss is acceptable.
     * **QoS 1 - At least once:** The message is delivered at least once. It ensures that the message arrives but may result in duplicates if the acknowledgment is lost.
     * **QoS 2 - Exactly once:** The message is delivered exactly once by using a handshake mechanism between the sender and receiver. This is the most reliable level but also the most resource-intensive.

