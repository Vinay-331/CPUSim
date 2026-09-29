# CSA CPUSim Practical
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

T0 : AR <- PC
T1 : IR <- M[AR], PC <- PC + 1
T2 : D0 ... D7 <- Decode IR(12-14), AR <- IR(0-11), I <- IR(15)

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

## Program

```
; ==============================================================
; Practical 3 : ADD operation on two user-entered numbers
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; Logic : SUM = A + B
; ==============================================================
 INP ; AC <- first number typed by the user
 STA A ; M[A] <- AC (save first number)
 INP ; AC <- second number
 ADD A ; AC <- AC + M[A], E <- carry out
 STA SUM ; M[SUM] <- AC (save the result)
 OUT ; display AC (the sum)
 HLT ; stop
A: .data 1 0 ; first number
SUM: .data 1 0 ; result
```

## After assembling and loading

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

# Practical 4: SUBTRACT Operation on Two User-entered Numbers

Aim-> To write an assembly program that reads two numbers A and B and displays A − B.
Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)

## Theory
The Basic Computer has no subtract instruction. Subtraction uses the two's complement: A − B = A + (B′ + 1).
CMA forms the 1's complement B′ and INC adds 1, giving −B, which is then added to A with ADD.

## Program

```
; ==============================================================
; Practical 4 : SUBTRACT operation on two user-entered numbers
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; Logic : DIFF = A - B = A + (2's complement of B)
; 2's complement of B = B' + 1 (CMA, then INC)
; ==============================================================
 INP ; AC <- A (minuend)
 STA A ; M[A] <- AC
 INP ; AC <- B (subtrahend)
 CMA ; AC <- AC' (1's complement of B)
 INC ; AC <- AC + 1 (2's complement of B = -B)
 ADD A ; AC <- A + (-B) = A - B
 STA DIFF ; M[DIFF] <- AC
 OUT ; display the difference
 HLT
A: .data 1 0 ; minuend
DIFF: .data 1 0 ; result
```

## After assembling and loading the program

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/6a4023ce-a034-48f6-a377-3393438c79cb" />

## Output after running the program and entering both numbers

<img width="673" height="247" alt="image" src="https://github.com/user-attachments/assets/d7944285-ffa0-400e-acae-2686cb1e1231" />

## Result

The output is correct, program takes the input, stores the input, subtracts the numbers using 2's complement method and displays the difference correctly. 

# Practical 5: Logical Operations: AND, OR, NOT, XOR, NOR, NAND

Aim To write an assembly program that performs AND, OR, NOT, XOR, NOR and NAND on two userentered numbers.
Tool CPU Sim 4.0.11 (Java 8 with JavaFX)

## Theory 
The Basic Computer provides only two logic instructions: AND (memory-reference, AC ← AC ∧ M[addr]) and CMA (register-reference, AC ← AC′). Since {AND, NOT} is functionally complete, every other operation can be built from them with Boolean algebra, applied to all 16 bits at once:

| Operation | Boolean identity used | Instruction sequence |
| :--- | :--- | :--- |
| A AND B | A·B | LDA A, AND B |
| A OR B | (A′·B′)′ (De Morgan) | LDA B, CMA, STA NB, LDA A, CMA, AND NB, CMA |
| NOT A | A′ | LDA A, CMA |
| A XOR B | (A + B)·(A·B)′ | LDA RAND, CMA, AND ROR |
| A NOR B | (A + B)′ | LDA ROR, CMA |
| A NAND B | (A·B)′ | LDA RAND, CMA |

## Program

```
; ==============================================================
; Practical 5 : Logical operations AND, OR, NOT, XOR, NOR, NAND
; on two user-entered numbers A and B
; Machine : BasicComputer.cpu (Mano's Basic Computer)
;
; The Basic Computer has only two logic instructions:
; AND (memory-reference) AC <- AC ^ M[addr]
; CMA (register-reference) AC <- AC'
; AND + NOT is a functionally complete set, so every other
; operation is built from them with Boolean algebra:
; NAND = (A.B)'
; OR = (A'.B')' (De Morgan)
; NOR = (A + B)'
; XOR = (A + B) . (A.B)'
; Outputs appear in this order: AND, OR, NOT A, NOT B, XOR, NOR, NAND
; ==============================================================
 INP ; AC <- A
 STA A
 INP ; AC <- B
 STA B
; ---------- AND = A . B ----------------------------------------
 LDA A ; AC <- A
 AND B ; AC <- A . B
 STA RAND
 OUT ; output 1 : A AND B
; ---------- OR = (A' . B')' ------------------------------------
 LDA B
 CMA ; AC <- B'
 STA NB ; NB <- B'
 LDA A
 CMA ; AC <- A'
 STA NA ; NA <- A'
Computer System Architecture – CPU Sim Lab Manual
Page 30
 AND NB ; AC <- A' . B'
 CMA ; AC <- (A' . B')' = A + B
 STA ROR
 OUT ; output 2 : A OR B
; ---------- NOT A, NOT B ---------------------------------------
 LDA NA
 OUT ; output 3 : NOT A
 LDA NB
 OUT ; output 4 : NOT B
; ---------- XOR = (A + B) . (A . B)' ---------------------------
 LDA RAND
 CMA ; AC <- (A . B)' = NAND
 STA RNAND
 AND ROR ; AC <- (A + B) . (A . B)'
 STA RXOR
 OUT ; output 5 : A XOR B
; ---------- NOR = (A + B)' -------------------------------------
 LDA ROR
 CMA ; AC <- (A + B)'
 STA RNOR
 OUT ; output 6 : A NOR B
; ---------- NAND = (A . B)' ------------------------------------
 LDA RNAND
 OUT ; output 7 : A NAND B
 HLT
A: .data 1 0
B: .data 1 0
NA: .data 1 0 ; A'
NB: .data 1 0 ; B'
RAND: .data 1 0 ; A AND B
ROR: .data 1 0 ; A OR B
RXOR: .data 1 0 ; A XOR B
RNOR: .data 1 0 ; A NOR B
RNAND: .data 1 0 ; A NAND B
```

## After assembling and loading the program

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/f305caea-002c-4b1b-bbcc-975fde6af4e7" />

## Output after running the program and entering both numbers

<img width="736" height="320" alt="image" src="https://github.com/user-attachments/assets/4a0a3378-54b1-4daa-b46f-1bb89c57a593" />

## Result

The program runs and takes both inputs correctly and stores them, All six logical operations were simulated using only AND and CMA. For A = 12 and B = 10 the outputs are AND = 8, OR = 14, NOT A = −13, NOT B = −11, XOR = 6, NOR = −15, NAND = −9

# Practical 6: Memory-reference Instructions: ADD, LDA, STA, BUN, ISZ

Aim-> To write an assembly program that simulates the memory-reference instructions ADD,LDA,STA, BUN and ISZ.
Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)

## Theory
A memory-reference instruction has an opcode 0–6 and a 12-bit address. During fetch AR ← IR(0–11), so at T4 onwards AR holds the address of the operand (the effective address, since I = 0).

| Symbol | Code | Execute micro-operations |
| :--- | :--- | :--- |
| ADD | 1xxx | DR ← M[AR]; AC ← AC + DR, E ← Cout |
| LDA | 2xxx | DR ← M[AR]; AC ← DR |
| STA | 3xxx | M[AR] ← AC |
| BUN | 4xxx | PC ← AR |
| ISZ | 6xxx | DR ← M[AR]; DR ← DR + 1; M[AR] ← DR; if DR = 0 then PC ← PC + 1 |

## Program

```
; ==============================================================
; Practical 6 : Memory-reference instructions ADD, LDA, STA, BUN, ISZ
; Machine : BasicComputer.cpu (Mano's Basic Computer)
;
; Task : multiply X by N using repeated addition.
; PROD = X + X + ... + X (N times)
; CTR holds -N; ISZ adds 1 to it on every pass and
; skips the BUN when it reaches 0, ending the loop.
; Data : X = 5, N = 3 (CTR = -3) -> PROD = 15
; ==============================================================
LOOP: LDA PROD ; AC <- M[PROD]
 ADD X ; AC <- AC + M[X]
 STA PROD ; M[PROD] <- AC
 ISZ CTR ; M[CTR] <- M[CTR] + 1; skip next if it became 0
 BUN LOOP ; PC <- LOOP (repeat)
 LDA PROD ; AC <- final product
 HLT
X: .data 1 5 ; multiplicand
CTR: .data 1 -3 ; -N (loop counter)
PROD: .data 1 0 ; product
```

## After assembling and loading the program

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/e5f7a1f8-e351-4e0b-902f-eacb95fb29c3" />

## After step 4 in debug mode:

<img width="588" height="512" alt="image" src="https://github.com/user-attachments/assets/66a1390b-c93e-48e8-a70c-4176fcf1efc3" />

## After step 5:

<img width="592" height="410" alt="image" src="https://github.com/user-attachments/assets/5e60c1aa-518d-4e73-ac88-ada79321303f" />

## After step 14:

<img width="573" height="431" alt="image" src="https://github.com/user-attachments/assets/17a82386-9a9d-48fc-af87-94c32fcc6c86" />

## After step 16:

<img width="686" height="807" alt="image" src="https://github.com/user-attachments/assets/3d07edbe-11d4-4e22-bc21-5cb88d092118" />

## Result

| Step | PC before | Instruction | IR (hex) | AC | DR | E | PC | AR | IR (dec) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 0 | LDA PROD | 2009 | 0 | 0 | 0 | 1 | 9 | 8201 |
| 2 | 1 | ADD X | 1007 | 5 | 5 | 0 | 2 | 7 | 4103 |
| 3 | 2 | STA PROD | 3009 | 5 | 5 | 0 | 3 | 9 | 12297 |
| 4 | 3 | ISZ CTR | 6008 | 5 | 65534 (-2) | 0 | 4 | 8 | 24584 |
| 5 | 4 | BUN LOOP | 4000 | 5 | 65534 (-2) | 0 | 0 | 0 | 16384 |
| 6 | 0 | LDA PROD | 2009 | 5 | 5 | 0 | 1 | 9 | 8201 |
| 7 | 1 | ADD X | 1007 | 10 | 5 | 0 | 2 | 7 | 4103 |
| 8 | 2 | STA PROD | 3009 | 10 | 5 | 0 | 3 | 9 | 12297 |
| 9 | 3 | ISZ CTR | 6008 | 10 | 65535 (-1) | 0 | 4 | 8 | 24584 |
| 10 | 4 | BUN LOOP | 4000 | 10 | 65535 (-1) | 0 | 0 | 0 | 16384 |
| 11 | 0 | LDA PROD | 2009 | 10 | 10 | 0 | 1 | 9 | 8201 |
| 12 | 1 | ADD X | 1007 | 15 | 5 | 0 | 2 | 7 | 4103 |
| 13 | 2 | STA PROD | 3009 | 15 | 5 | 0 | 3 | 9 | 12297 |
| 14 | 3 | ISZ CTR | 6008 | 15 | 0 | 0 | 5 | 8 | 24584 |
| 15 | 5 | LDA PROD | 2009 | 15 | 15 | 0 | 6 | 9 | 8201 |
| 16 | 6 | HLT | 7001 | 15 | 15 | 0 | 7 | 1 | 28673 |

The memory-reference instructions were simulated: LDA, ADD and STA computed the running product, ISZ counted the passes and skipped the branch when the counter reached zero, and BUN formed the loop.
Final AC = PROD = 15.

# Practical 7: Register-reference Instructions: CLA, CMA, CME, HLT

Aim-> To simulate the register-reference instructions CLA, CMA, CME and HLT and determine AC, E, PC, AR and IR in decimal after execution.
Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)

## Theory
Register-reference instructions have the code 7xxx: opcode 111 with I = 0. The low 12 bits select one operation on AC or E, executed at T3, with no memory access. Because the fetch routine always performs AR ← IR(0–11), AR ends up holding the low 12 bits of the instruction code (for example 800 hex = 2048 for CLA).

## Program
```
; ==============================================================
; Practical 7 : Register-reference instructions CLA, CMA, CME, HLT
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; Observe AC, E, PC, AR and IR (Decimal) after every instruction.
; ==============================================================
 LDA NUM ; set-up: AC <- 25 so that CLA has something to clear
 CLA ; 7800 : AC <- 0
 CMA ; 7200 : AC <- AC' (0000 -> FFFF = -1)
 CME ; 7100 : E <- E' (0 -> 1)
 HLT ; 7001 : S <- 1 (halt)
NUM: .data 1 25
```

## After assembling and loading the program

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/830021b2-41f1-4d26-9ef7-1312080ddd7f" />

## After step 1:

<img width="683" height="643" alt="image" src="https://github.com/user-attachments/assets/9e7618fe-6fec-49a9-b2dd-52e7d27366d0" />

## After step 2:

<img width="928" height="717" alt="image" src="https://github.com/user-attachments/assets/3da36a06-1b92-4ae3-8beb-d46ed686c269" />

## After step 3:

<img width="895" height="771" alt="image" src="https://github.com/user-attachments/assets/999f3c61-f13f-4808-a2d3-9d786ec4bf0b" />

## After step 4:

<img width="1076" height="840" alt="image" src="https://github.com/user-attachments/assets/23916546-dff6-44bb-8c2e-87619a300005" />

## After step 5:

<img width="722" height="985" alt="image" src="https://github.com/user-attachments/assets/2860b3ac-d662-4212-a9e8-911074e12270" />

## Result

**Register contents (decimal) after each instruction**

| Step | PC before | Instruction | IR (hex) | AC | E | PC | AR | IR (dec) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 0 | LDA NUM | 2005 | 25 | 0 | 1 | 5 | 8197 |
| 2 | 1 | CLA | 7800 | 0 | 0 | 2 | 2048 | 30720 |
| 3 | 2 | CMA | 7200 | 65535 (-1) | 0 | 3 | 512 | 29184 |
| 4 | 3 | CME | 7100 | 65535 (-1) | 1 | 4 | 256 | 28928 |
| 5 | 4 | HLT | 7001 | 65535 (-1) | 1 | 5 | 1 | 28673 |

**Final register contents after HLT**

| Register | Decimal | Hex | Explanation |
| :--- | :--- | :--- | :--- |
| AC | 65535 (signed -1) | FFFF | CLA cleared it, CMA complemented all bits |
| E | 1 | 1 | CME complemented E from 0 to 1 |
| PC | 5 | 005 | Address after HLT (HLT is at address 4) |
| AR | 1 | 001 | IR(0–11) of HLT = 001 |
| IR | 28673 | 7001 | Code of HLT |

After execution: AC = 65535 (−1), E = 1, PC = 5, AR = 1, IR = 28673.

# Practical 8: Register-reference Instructions: INC, SPA, SNA, SZE
