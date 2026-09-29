<img width="993" height="507" alt="image" src="https://github.com/user-attachments/assets/010a2a05-89e7-4578-8bd9-c8bff0b2e701" /># CSA CPUSim Practical
# Practical 1: Create a Machine (Basic Computer Architecture)
Aim-> To create, in CPU Sim, a machine based on the Basic Computer architecture: its registers,
memory, microinstructions, instruction fields and machine instructions.
Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)

## Theory

A CPU Sim machine is described at the register-transfer level by four kinds of objects:


| Object | Meaning | Dialog |
| :--- | :--- | :--- |
| Hardware modules | Registers, condition bits (single bits that can halt the machine or record a carry) and RAM. | Modify → Hardware Modules (Ctrl+K) |
| Microinstructions | Elementary register-transfer operations such as PC -> AR, M[AR] -> DR, AC+DR -> AC, a test-and-skip or a decode. | Modify → Microinstructions (Ctrl+Shift+M) |
| Fetch sequence | The microinstructions executed at the start of every instruction cycle (Practical 2). | Modify → Fetch Sequence (Ctrl+Y) |
| Machine instructions | A name, an opcode, a format built from fields and an **execute sequence** of microinstructions ending with **End**. | Modify → Machine Instructions (Ctrl+M) |

A control unit that runs a stored list of microinstructions for each instruction is a microprogrammed control
unit, which is exactly what CPU Sim simulates.
## Creating a new machine:

<img width="590" height="400" alt="image" src="https://github.com/user-attachments/assets/e0ab6717-b7ce-4161-aac1-74781c734f67" />



## Creating the registers:

<img width="1462" height="936" alt="image" src="https://github.com/user-attachments/assets/548a15f5-d2a9-4648-aa7b-833c1d97fbe4" />

## Creating the Condition Bits:

<img width="997" height="897" alt="image" src="https://github.com/user-attachments/assets/54da6f2e-e271-4793-9b71-35b9c553cc29" />

## Creating the RAM:

<img width="1241" height="1061" alt="image" src="https://github.com/user-attachments/assets/5b042690-8d35-4ee9-b444-90ad9aba9b7f" />

## Creating the microinstructions
## TransferRtoR:

<img width="883" height="698" alt="image" src="https://github.com/user-attachments/assets/e7ed16c4-9b4f-4268-af83-da107f8f473b" />

## MemoryAccess:

<img width="787" height="677" alt="image" src="https://github.com/user-attachments/assets/5a5f1554-7ccb-493e-ae6b-26028371044e" />

## Increment:

<img width="1006" height="767" alt="image" src="https://github.com/user-attachments/assets/5d77b1a6-a7f9-4fe9-85fb-acaa74efccc0" />

## Arithmetic:

<img width="696" height="627" alt="image" src="https://github.com/user-attachments/assets/d41b4d10-3303-4049-acba-fc2f01af673d" />

## Logical:

<img width="868" height="746" alt="image" src="https://github.com/user-attachments/assets/2ae3d416-5d78-4aba-b2d0-ef44649b721a" />

## Shift:

<img width="1178" height="898" alt="image" src="https://github.com/user-attachments/assets/a889d384-a5f5-4ccb-a34c-4fcb4e6a924e" />

## Set:

<img width="1133" height="832" alt="image" src="https://github.com/user-attachments/assets/6fd9076b-3296-4daf-bd74-4ebf6cc84228" />

## Test:

<img width="822" height="737" alt="image" src="https://github.com/user-attachments/assets/6569b1b7-8d7e-4640-be60-82a59e1b042c" />

## Decode:

<img width="870" height="783" alt="image" src="https://github.com/user-attachments/assets/5f8e223a-0f2e-4fa2-8296-cae69e69c19f" />

## SetCondBit:

<img width="1020" height="826" alt="image" src="https://github.com/user-attachments/assets/80e5ab67-5197-44cb-8690-e0c7166aaf57" />

## IO:

<img width="1291" height="885" alt="image" src="https://github.com/user-attachments/assets/4dffeffc-2e1a-4ce9-9774-68e3390d300c" />

## Creating the instruction field:

<img width="998" height="845" alt="image" src="https://github.com/user-attachments/assets/eee23375-9dcd-4a88-9a8b-94f71e354952" />

## Creating the machine instructions:

<img width="1528" height="1008" alt="image" src="https://github.com/user-attachments/assets/e253f9e5-89b9-421e-98a0-cb4b295eeb12" />
<img width="1055" height="881" alt="image" src="https://github.com/user-attachments/assets/145e1ada-38cb-4ab4-b818-77a63ec865e8" />

## Execute sequence of ADD:

<img width="1156" height="912" alt="image" src="https://github.com/user-attachments/assets/cb7b0032-460d-4279-9289-a2fc71d2e3d0" />

## Execute sequence of ISZ:

<img width="1035" height="883" alt="image" src="https://github.com/user-attachments/assets/5b6ad727-8824-4568-9b10-23eaa8b1c532" />

## Result:

A machine based on the Basic Computer architecture was created in CPU Sim and saved as
BasicComputer.cpu
 
Now, we will move onto practical 2, in which there is creation of Fetch sequence, program counter and saving and after that our basic computer will be completed and we can save our machine as BasicComputer.cpu

# Practical 2: Create the Fetch Routine of the Instruction Cycle
Aim-> To create the fetch (and decode) routine of the instruction cycle and observe it one microinstruction at a time.
Tool->  CPU Sim 4.0.11 (Java 8 with JavaFX)

## Theory
Every instruction cycle begins with the same fetch and decode phase. In Mano's Basic Computer it takes
three clock pulses, controlled by the sequence counter outputs T0, T1 and T2
```
T0 : AR <- PC
T1 : IR <- M[AR], PC <- PC + 1
T2 : D0 ... D7 <- Decode IR(12-14), AR <- IR(0-11), I <- IR(15)
```
## Creating fetch sequence instructions:

<img width="1217" height="988" alt="image" src="https://github.com/user-attachments/assets/e1e1689f-7e73-459a-a98c-3780d58a7037" />

## Testing the routine:

We have opened P03_ADD.a file in CPUSim and set the format of registers to unsigned Dec

<img width="1896" height="1176" alt="image" src="https://github.com/user-attachments/assets/448e0a0a-7337-4379-a1f8-0cef16c06856" />

Now, we will click step by micro 5 times to see the register changed by each instruction
## After clicking step by micro 5  times:

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/0c0408bd-8604-468f-9469-ccd980f477c9" />

## Result:

### Observations Table

| Micro-step | Microinstruction | AR | PC | IR |
| :--- | :--- | :--- | :--- | :--- |
| **start** | -- | 0 | 0 | 0 |
| **1** | `PC->AR` | 0 | 0 | 0 |
| **2** | `M[AR]->IR` | 0 | 0 | 63488 (F800) |
| **3** | `PC+1->PC` | 0 | 1 | 63488 |
| **4** | `IR(0-11)->AR` | 2048 (800) | 1 | 63488 |
| **5** | `decode-IR` | 2048 | 1 | 63488 -> INP |

The fetch routine PC->AR, M[AR]->IR, PC+1->PC, IR(0-11)->AR, decode-IR was created and
verified by single-stepping the first instruction of a program.

# Practical 3: ADD Operation on Two User-entered Numbers

Aim-> To write an assembly program that reads two numbers entered by the user, adds them and displays the sum.
Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)

## Theory

INP reads an integer into AC. STA A saves it in memory because the next INP overwrites AC. ADD A is a memory-reference instruction: DR ← M[A], then AC ← AC + DR and the carry out of bit 15 goes to E. OUT displays AC and HLT stops the machine.
Numbers are 16-bit two's complement, so the range is −32768 to +32767

The program that we will be using:
<img width="993" height="507" alt="image" src="https://github.com/user-attachments/assets/fdb4a801-9370-4fe3-a389-042dff11180d" />

## After assembling and loading (Ctrl+2)

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/7b4a6cf8-a7ba-499c-a64e-ff0acdf40b99" />


Changed IR(0-11)->AR to srcStartBit = 0 and destStartBit = 0 so CPU Sim maps the address correctly to RAM instead of shifting it

## After running
<img width="602" height="330" alt="image" src="https://github.com/user-attachments/assets/5be2533e-20b5-4c67-8b65-9ddc2de4f25b" />

After giving first input:

<img width="527" height="117" alt="image" src="https://github.com/user-attachments/assets/f3bb31c8-f6db-446c-a4f9-735debb6bf70" />

After giving second input:

<img width="690" height="178" alt="image" src="https://github.com/user-attachments/assets/e740f7a3-b426-45bb-a2d9-c19f03bb81db" />

## Result

The output is correct, program takes the input, stores the input, adds the numbers and displays the sum correctly. 
