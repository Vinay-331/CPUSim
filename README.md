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

Aim-> To simulate INC, SPA, SNA and SZE and determine AC, E, PC, AR and IR in decimal after execution.
Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)

## Theory

A skip instruction increments PC once more when its condition is true, so the next instruction is not executed. In the program every skip instruction is followed by a HLT “trap”: the program reaches its last instruction only if every skip works. AC starts at −2 so that both a negative and a non-negative value are tested.

## Program

```
; ==============================================================
; Practical 8 : Register-reference instructions INC, SPA, SNA, SZE
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; A skip instruction adds 1 to PC when its condition is true, so
; the instruction after it is NOT executed. Each HLT below is a
; "trap": the program only reaches the final HLT if every skip works.
; ==============================================================
 LDA NUM ; set-up: AC <- -2
 INC ; 7020 : AC <- AC + 1 (-2 -> -1)
 SNA ; 7008 : AC < 0 (negative) -> skip next
 HLT ; (skipped)
 INC ; 7020 : AC <- AC + 1 (-1 -> 0)
 SPA ; 7010 : AC(15) = 0 (positive) -> skip next
 HLT ; (skipped)
 SZE ; 7002 : E = 0 -> skip next
 HLT ; (skipped)
 INC ; 7020 : AC <- AC + 1 (0 -> 1)
 HLT ; 7001 : halt
NUM: .data 1 -2
```

## After assembling and loading

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/16fe6237-5ed1-4796-bcca-4bf45fbece58" />

## After step 1:

<img width="905" height="642" alt="image" src="https://github.com/user-attachments/assets/840ec8e2-7441-481d-ae11-ff46a77e66bc" />

## After step 2:

<img width="772" height="607" alt="image" src="https://github.com/user-attachments/assets/156e8c69-17f2-4d04-825e-0c3716e1881c" />

## After step 3:

<img width="807" height="681" alt="image" src="https://github.com/user-attachments/assets/ed1b70e0-5140-439e-ac77-6702a7579447" />

## After step 4:

<img width="790" height="680" alt="image" src="https://github.com/user-attachments/assets/0af461ec-3a6f-4b9a-a828-38f5aed2ca00" />

## After step 5:

<img width="898" height="775" alt="image" src="https://github.com/user-attachments/assets/62cdb0f1-0dec-4aba-998b-8c09c43855b8" />

## After step 6:

<img width="831" height="677" alt="image" src="https://github.com/user-attachments/assets/d96a689d-97f8-4445-9ff9-0f02fcb00f57" />

## After step 7:

<img width="765" height="737" alt="image" src="https://github.com/user-attachments/assets/40ca36f2-597d-4568-a5a0-3f1b3b22276d" />

## After step 8:

<img width="721" height="875" alt="image" src="https://github.com/user-attachments/assets/e9d912a7-37c8-4b3d-b680-8f5602cf2e52" />

## Result

| Step | PC before | Instruction | IR (hex) | AC | E | PC | AR | IR (dec) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 0 | LDA NUM | 200B | 65534 (-2) | 0 | 1 | 11 | 8203 |
| 2 | 1 | INC | 7020 | 65535 (-1) | 0 | 2 | 32 | 28704 |
| 3 | 2 | SNA | 7008 | 65535 (-1) | 0 | 4 | 8 | 28680 |
| 4 | 4 | INC | 7020 | 0 | 0 | 5 | 32 | 28704 |
| 5 | 5 | SPA | 7010 | 0 | 0 | 7 | 16 | 28688 |
| 6 | 7 | SZE | 7002 | 0 | 0 | 9 | 2 | 28674 |
| 7 | 9 | INC | 7020 | 1 | 0 | 10 | 32 | 28704 |
| 8 | 10 | HLT | 7001 | 1 | 0 | 11 | 1 | 28673 |

INC, SPA, SNA and SZE were simulated and every skip was verified. After execution: AC = 1, E = 0, PC = 11, AR = 1, IR = 28673.

# Practical 9: Register-reference Instructions: CIR, CIL

Aim-> To simulate CIR and CIL and determine AC, E, PC, AR and IR in decimal after execution.
Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)

## Theory
CIR and CIL circulate (rotate) the 17-bit combination of E and AC by one position:

CIR (7080): E -> AC(15) -> AC(14) -> ... -> AC(0) -> E (rotate right)
CIL (7040): E <- AC(15) <- AC(14) <- ... <- AC(0) <- E (rotate left)

No bit is lost, so a CIR followed by a CIL restores the original AC and E. In CPU Sim each rotation uses a 1-bit scratch register TMP: the bit leaving AC is saved in TMP, AC is shifted, the old E enters the vacated bit, and TMP is copied into E.

## Program

```
; ==============================================================
; Practical 9 : Register-reference instructions CIR, CIL
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; CIR : circulate E and AC right (E -> AC(15), AC(0) -> E)
; CIL : circulate E and AC left (AC(15) -> E, E -> AC(0))
; ==============================================================
 LDA NUM ; set-up: AC <- 9 = 0000 0000 0000 1001, E = 0
 CIR ; 7080 : AC = 0000 0000 0000 0100 (4), E = 1
 CIR ; 7080 : AC = 1000 0000 0000 0010 (-32766), E = 0
 CIL ; 7040 : AC = 0000 0000 0000 0100 (4), E = 1
 CIL ; 7040 : AC = 0000 0000 0000 1001 (9), E = 0
 HLT
NUM: .data 1 9
```

## After assembling and loading

<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/5e0b11f0-0605-4f6c-b7b6-6120286f7675" />

## After step 1:

<img width="1387" height="745" alt="image" src="https://github.com/user-attachments/assets/8caf4fb6-6dd3-4106-a1fb-d0d109b8149f" />

## After step 2:

<img width="862" height="772" alt="image" src="https://github.com/user-attachments/assets/b362e353-50da-4f90-bad5-16e5b5a2aa2d" />

## After step 3:

<img width="770" height="698" alt="image" src="https://github.com/user-attachments/assets/cc38641a-6eec-4105-88cb-74f94ea83868" />

## After step 4:

<img width="751" height="606" alt="image" src="https://github.com/user-attachments/assets/50a6a32a-3026-4469-ade1-8280c68daf4b" />

## After step 5:

<img width="796" height="753" alt="image" src="https://github.com/user-attachments/assets/012c43df-e67b-4833-b5a5-aa69fd2daaeb" />

## After step 6:

<img width="773" height="893" alt="image" src="https://github.com/user-attachments/assets/79c61be4-8bae-49ea-83b5-f5b11dc72227" />


## Result

| Step | PC before | Instruction | IR (hex) | AC | E | PC | AR | IR (dec) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | 0 | LDA NUM | 2006 | 9 | 0 | 1 | 6 | 8198 |
| 2 | 1 | CIR | 7080 | 4 | 1 | 2 | 128 | 28800 |
| 3 | 2 | CIR | 7080 | 32770 (-32766) | 0 | 3 | 128 | 28800 |
| 4 | 3 | CIL | 7040 | 4 | 1 | 4 | 64 | 28736 |
| 5 | 4 | CIL | 7040 | 9 | 0 | 5 | 64 | 28736 |
| 6 | 5 | HLT | 7001 | 9 | 0 | 6 | 1 | 28673 |

CIR and CIL were simulated; two right rotations followed by two left rotations restored AC = 9. After execution: AC = 9, E = 0, PC = 6, AR = 1, IR = 28673. After each individual instruction the values are as in the table above.

# Practical 10: Sum of Integers until a Negative Number is Read

Aim-> To write an assembly program that reads integers and adds them until a negative non-zero number is read, then outputs the sum (not including the last number).
Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)

## Theory

This is a sentinel-controlled loop: the negative number marks the end of the data. After each INP, SPA skips the exit branch when AC ≥ 0; for a negative number the skip does not happen and BUN DONE leaves the loop before the number is added. Zero counts as non-negative, so it is added (it does not change the sum).

## Program

```
; ==============================================================
; Practical 10 : Read integers and add them until a negative
; non-zero number is read; output the sum
; (the negative number is NOT included).
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; ==============================================================
LOOP: INP ; AC <- next number
 SPA ; if AC >= 0 skip the exit branch
 BUN DONE ; AC < 0 : leave the loop
 ADD SUM ; AC <- AC + SUM
 STA SUM ; SUM <- AC
 BUN LOOP ; read the next number
DONE: LDA SUM ; AC <- SUM
 OUT ; display the sum
 HLT
SUM: .data 1 0 ; running total
```
## After assembling and loading the program

<img width="1917" height="1177" alt="image" src="https://github.com/user-attachments/assets/0537e34d-1a88-4eea-8971-e2e64fa71ae0" />

## Output after running the program and giving inputs 4, 10, 0, 6 and finally -3

<img width="723" height="441" alt="image" src="https://github.com/user-attachments/assets/4b563a28-5e67-4dfa-9cde-f5de113c212f" />

## Result
The program successfully keeps running until a negative input is given, in the case above, The program adds integers until a negative number is read and displays the sum excluding it: 4 + 10 + 0 + 6 = 20.

# Practical 11: Sum of Integers until Zero is Read

Aim-> To write an assembly program that reads integers and adds them until zero is read, then outputs the sum.
Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)

## Theory
Here the sentinel is 0. SZA skips the next instruction when AC = 0. Because a skip can only jump over one instruction, two branches are used: when AC ≠ 0 the BUN ADDIT executes and the number is added; when AC = 0 that branch is skipped and BUN DONE ends the loop. Negative numbers are added normally.

## Program
```
; ==============================================================
; Practical 11 : Read integers and add them until zero is read;
; then output the sum.
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; ==============================================================
LOOP: INP ; AC <- next number
 SZA ; if AC != 0 do not skip ...
 BUN ADDIT ; ... so go and add it
 BUN DONE ; AC = 0 (BUN ADDIT was skipped) : finish
ADDIT: ADD SUM ; AC <- AC + SUM
 STA SUM ; SUM <- AC
 BUN LOOP ; read the next number
DONE: LDA SUM ; AC <- SUM
 OUT ; display the sum
 HLT
SUM: .data 1 0 ; running total
```

## After assembling and loading the program
<img width="1917" height="1198" alt="image" src="https://github.com/user-attachments/assets/1da540a1-ccaa-4a57-9d1a-372e48cb7087" />

## Output after running the program and giving inputs 8, 12, -5 and finally 0

<img width="902" height="552" alt="image" src="https://github.com/user-attachments/assets/d895241e-7faa-4a3d-87fd-1c04a7e8e2e7" />

## Result
The program successfully keeps running until 0 is given as input, in the case above, The program adds integers until 0 is read and displays the sum: 8 + 12 + (−5) = 15.

