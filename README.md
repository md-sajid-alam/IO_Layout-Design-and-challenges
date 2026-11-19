# IO_Layout-Design-and-challenges
Design of 7nm IO and Challenges faced while making

## Layout Screenshot of complete IO
<img width="1463" height="473" alt="image" src="https://github.com/user-attachments/assets/5ef37a8b-76f4-41ae-a099-e1dab8b5943c" />



## Schematic of IO Circuitry
<img width="1187" height="1325" alt="Black-and-White SRAM Circuit Schematic" src="https://github.com/user-attachments/assets/609dde32-bacd-45f0-b96d-714d1bb841b3" />


IO Schematic majorly has the following segment which needs to be take care while making the IO Layout

A) Circuit Common to Read and Write

    1. Pre-charge and equalizer
    
      ► It should be made symmetrical and in one bit cell pitch
      ► Pre-charge signal should be symmetrical to BT and BC to cancel coupling
      
    2. Mux
    
      ► It should be made symmetrical and in one bit cell pitch
      ► Mux signal should be connected symmetrical to BT and BC to cancel coupling

## Layout Screenshot of Precharge and Mux
<img width="1463" height="473" alt="image" src="https://github.com/user-attachments/assets/89acbce9-e8ad-4bda-b2e6-19aec23e4890" />



B) Circuit Specific to Read

    1. Sense
      ► It should be common centroid
      ► Guard ring to reduce body voltage fluctuation
      ► ST and SC (Sense internal node signals)
          o Be matched in load
          o Should be least loaded to increase discharge
          o Shielded with dynamic signals like SEN, PCH, WCLK, MUX, SENPCH
          
    2. Sense – Enable generation
      ► To be made such that nodes should not couple with ST or ST
      
    3. Sense – pre-charge
      ► To be made such that nodes should not couple with ST or ST
      ► Pre-charge and equalizer to be made symmetrical to ST and SC
      
    4. Output Driving Stage
      ► To made near boundary of IO layout to have easy access to Q

## Layout Screenshot of Sense Amplifier with common centroid matching
<img width="432" height="628" alt="WhatsApp Image 2026-11-19 at 16 22 01" src="https://github.com/user-attachments/assets/34501d04-9a75-40c8-918f-6587c222e932" />


## Layout Screenshot of Read circuitry
<img width="589" height="692" alt="image" src="https://github.com/user-attachments/assets/484faa3a-66b6-46e8-9f1c-1d98fbdc43d5" />



C) Circuit Specific to Write

    ► Connection to Bit lines should be small to reduce bit-line load
    ► Bit lines should not be exposed to signal while connecting write mux or write driver
    ► Data Latch to be made near boundary of IO layout to have easy access to Data and Mask pins
## Layout Screenshot of Write Circuitry
<img width="1354" height="719" alt="image" src="https://github.com/user-attachments/assets/c29c70b5-3e6c-44c4-9fc7-5d56a7de2d72" />



