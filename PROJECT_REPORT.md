# PulseGrid: Wireless Sensor Network Monitoring System

## 1. Abstract
PulseGrid is a web-based monitoring dashboard concept for a Wireless Sensor Network (WSN). A WSN contains distributed sensor nodes that measure environmental or physical conditions and forward readings wirelessly to a coordinator or gateway. The dashboard brings sensor readings, node status, battery levels, signal strength, topology, analytics, and alerts into one interface. The current version uses generated demonstration data so it can be run without hardware.

## 2. Problem statement
In a sensor-based environment, checking every node individually is inconvenient. A node may stop reporting, its battery may become low, or its wireless link may weaken without an obvious central view. PulseGrid demonstrates a central dashboard where a user can inspect the status of multiple nodes and identify conditions that may need attention.

## 3. Objectives
- Display multiple sensor nodes in a single interface.
- Visualize sample temperature and humidity readings.
- Represent wireless link quality using RSSI-style values in dBm.
- Show battery levels and node availability.
- Illustrate a star topology with a gateway and sensor nodes.
- Raise and acknowledge demo alerts.
- Export sample readings to CSV for further analysis.
- Provide a responsive interface for phones and computers.

## 4. System modules
1. **Overview module:** summarizes connected nodes, average signal, environmental readings, alerts, and estimated network health.
2. **Sensor node module:** lists node IDs, locations, status, temperature, humidity, battery, RSSI, and last-seen time; supports search and status filtering.
3. **Topology module:** visualizes the gateway and links to each sensor node. Link styles indicate stable, weak, or offline status.
4. **Analytics module:** compares current temperatures, groups nodes by signal band, and displays a dataset preview.
5. **Alert module:** displays threshold events, allows acknowledgement, and can create a demo event.
6. **CSV export module:** downloads node readings in a spreadsheet-friendly format.

## 5. Technologies used
- HTML5 for page structure.
- CSS3 for responsive layout, dashboard cards, status labels, and topology styling.
- JavaScript for generated sensor values, interaction, chart rendering, filtering, and export.
- HTML Canvas API for the trend chart.
- Browser Blob and download APIs for CSV export.

## 6. Working methodology
1. The application initializes a collection of sample sensor nodes.
2. Each node contains an ID, location, temperature, humidity, battery percentage, RSSI value, and status.
3. A timer updates online node values to imitate incoming telemetry.
4. The interface recalculates averages and health indicators.
5. The user can open the node list, search for a node, filter by status, and inspect the network map.
6. The alert screen lists events that have not been acknowledged.
7. The user can download the node table as a CSV file.

## 7. Wireless communication concepts demonstrated
- **Sensor node:** a device that measures a physical condition.
- **Gateway/coordinator:** a central point that collects or forwards node data.
- **RSSI:** Received Signal Strength Indicator, commonly expressed in dBm. Values closer to 0 are generally stronger, although interpretation depends on the radio technology and environment.
- **Topology:** the arrangement of devices and communication links. This project illustrates a star topology.
- **Latency:** the time taken for data to travel from source to destination. The displayed value is only an estimate in this demo.
- **Packet delivery ratio:** the proportion of transmitted packets successfully received. The displayed value is illustrative, not measured.
- **Duty cycle and battery:** sensor nodes often conserve energy by sleeping between measurements or transmissions.

## 8. Sample alert rules
- Temperature above 32°C.
- Humidity above 80%.
- RSSI weaker than −80 dBm.
- Battery below 20%.
- A node is marked offline when it stops reporting in a real implementation.

These are illustrative project thresholds and should be changed to suit a real sensor and environment.

## 9. Testing checklist
- Open the dashboard in a modern browser.
- Verify all five navigation views open.
- Pause and resume simulation.
- Search for a sensor by name or ID.
- Filter online, warning, and offline nodes.
- Rebuild the topology map.
- Create a demo alert and acknowledge it.
- Add a demo sensor node.
- Export the CSV and open it in a spreadsheet application.
- Resize the browser to verify the mobile layout.

## 10. Limitations and future scope
This prototype does not connect to physical sensor hardware, scan nearby wireless networks, or collect real RF measurements. All values are generated locally. A production implementation could use ESP32 sensor nodes, a Wi-Fi or Zigbee link, MQTT, a Node.js/Express backend, a database, user authentication, persistent historical charts, configurable alert thresholds, and real-time WebSocket updates. The gateway could publish telemetry to an MQTT broker, while the backend stores readings and serves them to the dashboard through an API.

## 11. Conclusion
PulseGrid demonstrates the interface and basic monitoring workflow of a Wireless Sensor Network Monitoring System. It combines sensor status, environmental readings, wireless signal indicators, a topology map, alerts, analytics, and CSV export in a responsive web application. It is suitable as a software demonstration for a Wireless and Mobile Communication mini project and can be extended with actual sensors and a backend.

## 12. Viva questions with short answers
**Q1. What is a WSN?** A Wireless Sensor Network is a group of sensor nodes that monitor conditions and communicate wirelessly.

**Q2. What is a sensor node?** A node is a device that contains sensing, processing, power, and wireless communication components.

**Q3. What is a gateway?** A gateway collects data from nodes and can forward it to a server or application.

**Q4. What does RSSI indicate?** It is an indicator of received radio signal strength, often expressed in dBm.

**Q5. Why is battery monitoring important?** Many sensor nodes are battery-powered, so low battery can interrupt data collection.

**Q6. What topology is shown?** A star topology, where nodes communicate with a central gateway.

**Q7. What is the purpose of alerts?** Alerts highlight conditions such as weak signal, high temperature, or low battery.

**Q8. Are the values in this version real?** No. They are generated sample values. Real readings require connected sensor hardware and a data gateway/API.
