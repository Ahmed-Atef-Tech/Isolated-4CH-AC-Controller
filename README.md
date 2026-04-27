# Isolated-4CH-AC-Controller
ISO-AC4-FB: 4-Channel isolated AC controller (220V/8A) designed in KiCad. Features SSRs, active AC feedback, 1oz copper, and strict safety isolation.

<img width="4000" height="3000" alt="IMG_20260427_044305" src="https://github.com/user-attachments/assets/db4fcc82-b6e6-4d9f-828a-f497906705eb" />

<img width="4960" height="3507" alt="image" src="https://github.com/user-attachments/assets/680f9557-975e-4685-8515-320466292683" />

<img width="3130" height="1986" alt="ISO-AC4-FB Controller_page-0001" src="https://github.com/user-attachments/assets/d99de86e-e3c4-41ab-bdb6-01920e405c57" />

<img width="1724" height="968" alt="ISO-AC4-FB Controller1" src="https://github.com/user-attachments/assets/8354bb90-e9a3-404f-8f61-9492dd49474a" />

<img width="1724" height="968" alt="ISO-AC4-FB Controller" src="https://github.com/user-attachments/assets/cde40606-4e93-45b1-aba5-ce1b0d3c8c7a" />


<img width="666" height="330" alt="image" src="https://github.com/user-attachments/assets/07a1809f-2456-4d7c-9783-cb38e3806429" />


### 🔧 Known Limitations and Proposed Revisions (Rev 2.0)

**1. AC Routing Topology & Isolation Constraints**
* **Current Implementation:** Due to strict board size constraints in this initial prototype, the 220V `AC_N` line (used strictly for low-current voltage sensing/feedback) and the 5V `VCC` logic line were routed using a Daisy-Chain topology. Trace widths were set to 0.5mm, which is electrically sufficient for the minimal control current (~10mA).
* **Engineering Assessment:** While the current capacity is well within safe margins for a 1oz copper board, I am fully aware that the daisy-chain approach in the high-voltage section makes it difficult to maintain optimal IPC-2221 clearance distances. Relying solely on soldermask for high-voltage separation is not ideal for long-term industrial reliability.
* **Action Plan for Production (Rev 2.0):** The next revision will transition the high-voltage routing to a **Star Topology** directly from the input terminal. Furthermore, isolation milling slots will be implemented between the interconnected AC nodes to strictly enforce standard creepage distances.

**2. Wireless Connectivity & IoT Integration**
* **Action Plan for Rev 2.0:** The current prototype relies on an external microcontroller connected via pin headers. In the next revision, the component placement and routing will be heavily optimized to include a dedicated socket for an **ESP-01 module** (or a fully integrated **ESP8266/ESP32** circuit). This will allow the PCB to act as a standalone, plug-and-play IoT shield, enabling seamless Wi-Fi control and smart home integration right out of the box without any external wiring.

**3. Mechanical Design & Productization**
* **Action Plan for Rev 2.0:** To bridge the gap between a bare PCB and a consumer-ready device, a custom **3D-printable enclosure** will be designed. This will provide a professional aesthetic, ensure secure mounting, and most importantly, guarantee physical isolation and safety from high-voltage AC contacts for the end-user.

**4. Schematic Refactoring & Annotation Optimization**
* **Action Plan for Rev 2.0:** The schematic diagram will be completely refactored to enhance readability and logical flow. Component designators will be systematically re-annotated and grouped by functional blocks (e.g., sequentially per channel). This structured approach will significantly simplify troubleshooting, improve the BOM organization, and streamline the overall PCB assembly process.


