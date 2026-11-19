# IO_Layout-Design-and-challenges
Design of 7nm IO and Challenges faced while making

## Layout Screenshot of complete IO
<img width="1853" height="990" alt="Screenshot from 2026-11-19 10-42-52" src="https://github.com/user-attachments/assets/5f4d7ef2-e13b-4c68-89fd-402c347ea3fe" />


## Schematic of IO Circuitry
<img width="741" height="827" alt="image" src="https://github.com/user-attachments/assets/01649c59-2d5b-4d64-b874-21c0353277e3" />

IO Schematic majorly has the following segment which needs to be take care while making the IO Layout

A) Circuit Common to Read and Write

    1. Pre-charge and equalizer
    
      ► It should be made symmetrical and in one bit cell pitch
      ► Pre-charge signal should be symmetrical to BT and BC to cancel coupling
      
    2. Mux
    
      ► It should be made symmetrical and in one bit cell pitch
      ► Mux signal should be connected symmetrical to BT and BC to cancel coupling

## Layout Screenshot of Precharge and Mux
<img width="1853" height="990" alt="Screenshot from 2026-11-19 10-43-15" src="https://github.com/user-attachments/assets/efa97833-a352-4e3e-bda0-6340bb0b5ba3" />


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
<img width="1853" height="990" alt="Screenshot from 2026-11-19 10-48-03" src="https://github.com/user-attachments/assets/dd771b79-1932-4ac3-93cd-e29fd2372ca5" />

## Layout Screenshot of Read circuitry
<img width="1853" height="990" alt="Screenshot from 2026-11-19 10-52-28" src="https://github.com/user-attachments/assets/a21ba0f7-0c23-4da5-b3c3-61644f5ac59d" />


C) Circuit Specific to Write

    ► Connection to Bit lines should be small to reduce bit-line load
    ► Bit lines should not be exposed to signal while connecting write mux or write driver
    ► Data Latch to be made near boundary of IO layout to have easy access to Data and Mask pins
## Layout Screenshot of Write Circuitry
<img width="1853" height="990" alt="Screenshot from 2026-11-19 10-52-46" src="https://github.com/user-attachments/assets/b1fabb46-9d3b-4db6-bbad-940a9ca0374d" />


