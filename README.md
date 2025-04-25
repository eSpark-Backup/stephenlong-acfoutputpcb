# ACF Output PCB
####  Client Name: Stephen Long Jr.

## Project Requirements
This project involves the PCB layout design for the ACF Output PCBA, a daughter board of the ACF system. The Output PCBA serves as the main I/O interface for DMX and Ethernet signals and includes electrical connections to the system’s external circular connector and a board-to-board interface with the ACF User Interface PCBA via a Bridge PCBA. The core features and selected parts information is mentioned below:
- Connectors
    - DMX Input Connector:
        - Part Number: NC5MBV-B (5-pin male XLR)
    - DMX Output Connector:
        - Part Number: NC5FBV-B (5-pin female XLR)
    - DMX input/output circuitry
        - Add the SM712 very close to the "outside world" connector for the DMX. It is a very basic TVS protection in case the customer would connect a wrong cable to the line. This TVS will protect the electronics. I think it is the best place for the protections.
![image](https://github.com/user-attachments/assets/7071e028-4c34-45a1-bdcf-22a9ca64caee)

- Ethernet Connectors x 2
    - Part Number: NE8FBV-C5-LED (EtherCON RJ45 receptacles with integrated light pipes)
        - Please add those resistors and capacitors next to the ethernet connectors.
        - And also add a TVS protection on each RS485 differential pair, we usually use the SM712
- Board to Board Data x 2
    - Part Number: SSW-110-02-G-D-RA-N Mfr.: Samtec
    - User Interface PCBA for reference:
![image](https://github.com/user-attachments/assets/a93cce57-ea25-4116-9c70-b5d211468c1b)
- LED Indicators for Ethernet
    - Each RJ45 port requires:
        - Left LED (Green): Indicates active link
        - Right LED (Yellow): Indicates data activity
    - LEDs will be SMD-mounted under the NE8FBV-C5-LED light pipe window.
        - Placement and routing shall follow manufacturer light pipe guidelines.
- Board-to-Board Interface (to Bridge PCBA)
    - Include a board-to-board header to connect with the Bridge PCBA.
![image](https://github.com/user-attachments/assets/030705fd-4451-4e64-96a1-729e3b509175)
- Circular Connector Output Header
    - 8-pin output header for external panel connection:
        - 2x 24V lines (14AWG)
        - 2x GND (14AWG)
        - 4x differential data pair (twisted pair) to panels (26AWG) (total of 8 wires)
        - 8A current capacity for power lines
![image](https://github.com/user-attachments/assets/819f064f-dfa1-48e8-9fa3-8ff628941cdf)
    - Pinout and mechanical dimensions will be confirmed during layout phase
### Pin Number Reference Photos
![image](https://github.com/user-attachments/assets/68f21b23-1c99-4672-b4e2-2857b27c3b59)

![image](https://github.com/user-attachments/assets/36844f65-391e-40a1-895d-61ac667d1af3)

![image](https://github.com/user-attachments/assets/012347be-37a9-4f47-b0e0-932dbcb324d1)

**Note:** The new LEDs coming from the W5500 and the "GND_DRIVE" will be the signals for driving the LEDs on the ethernet connections. They are pins 4-5-6 on the J10 connectors. Also mention that the P1LED and P2LED should drive via the "GND_DRIVE" pin (one side to PxLED an the other to "GND_DRIVE".

### Assumptions and Constraints
- The ACF Output PCBA will not contain any microcontrollers or active control logic; it is a passive I/O board.
- All firmware, control logic, and display interfacing is handled by the ACF UI PCBA.
- Mechanical constraints must be confirmed early in the layout process to ensure connector alignment and clearance

### Product Concept Images
![image](https://github.com/user-attachments/assets/295b08e8-68b4-49c5-a36c-e511325e1ceb)

![image](https://github.com/user-attachments/assets/3072cbdf-d4a5-4b4c-b056-756014323da4)

![image](https://github.com/user-attachments/assets/2cb7703a-f901-4e8c-bbca-153c7dfa8fe1)
