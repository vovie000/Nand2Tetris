# About the Software
The Nand2tetris Software Suite consists of two directories: projects, and tools.

The [**projects**](https://github.com/vovie000/Nand2Tetris/tree/main/Software/projects) directory is divided into 14 project directories named 00, 01, ..., 13 (of which project 00 is relevant only to learners who take the course in Coursera, and project 13 is open-ended). These directories contain files that you have to modify and complete as you work on various nand2tetris projects.

The [**tools**](https://github.com/vovie000/Nand2Tetris/tree/main/Software/tools) directory contains the nand2tetris software tools. It's a collection of programs and files that will be explained as you follow the various projects.

The [**reference**](https://github.com/vovie000/Nand2Tetris/tree/main/Software/reference) directory contains instructions and manuals on various tools.

**The remainder of this section should be used as reference**; there is no need to read what follows until you will be asked to use a particular software tool.

**The .bat and .sh files** are batch and script files, used to invoke the nand2tetris software tools. These files are explained in detail below.

**The bin directory** contains the code of the nand2tetris software tools. It consists of several subdirectories containing Java class files and supporting files.

**The builtInChips and the builtInVMCode directories** contain files that are used by the supplied Hardware Simulator and VM Emulator, respectively.

**The OS directory** contains a compiled version of the Jack operating system.

<br><br/><br><br/>

# Software Tools
## Hardware Simulator
Simulates and tests logic gates and chips implemented in the HDL (Hardware Description Language) described in the book. Used in hardware construction projects.

Hardware Simulator Tutorial:

[![][ppt]](https://github.com/vovie000/Nand2Tetris/blob/main/Software/reference/Hardware%20Simulator%20Tutorial.pdf)
[![][pdf]](https://github.com/vovie000/Nand2Tetris/blob/main/Software/reference/Hardware%20Simulator%20Tutorial.pdf)

## CPU Simulator
Emulates the operation of the Hack computer system. Used to test and run programs written in the Hack machine language, in both its binary and assembly versions.

CPU Simulator Tutorial:

[![][ppt]](https://github.com/vovie000/Nand2Tetris/blob/main/Software/reference/CPU%20Emulator%20Tutorial.ppt)
[![][pdf]](https://github.com/vovie000/Nand2Tetris/blob/main/Software/reference/CPU%20Emulator%20Tutorial.pdf)


## VM Emulator
Emulates the operation of our virtual machine (similar to Java's JVM); used to run and test programs written in the VM language (similar to Java's Bytcode).

VM Emulator Tutorial:

[![][ppt]](https://github.com/vovie000/Nand2Tetris/blob/main/Software/reference/VM%20Emulator%20Tutorial.ppt)
[![][pdf]](https://github.com/vovie000/Nand2Tetris/blob/main/Software/reference/VM%20Emulator%20Tutorial.pdf)

## Assembler
Translates programs from the Hack assembly language to Hack binary code. The resulting code can be executed directly on the Computer chip (in the hardware simulator), or emulated on the supplied CPU Emulator (much faster and more convenient).

Assembler Tutorial:

[![][ppt]](https://github.com/vovie000/Nand2Tetris/blob/main/Software/reference/Assembler%20Tutorial.ppt)
[![][pdf]](https://github.com/vovie000/Nand2Tetris/blob/main/Software/reference/Assembler%20Tutorial.pdf)

[ppt]: https://github.com/vovie000/Nand2Tetris/raw/main/misc/Icons/PowerPoint.png "PPT Presentation"

[pdf]: https://github.com/vovie000/Nand2Tetris/raw/main/misc/Icons/pdf.png "Raw PDF"

## Compiler
Translates programs written in Jack (a simple, Java-like object-based language) into VM code. The resulting code can run on the supplied VM Emulator. Alternatively, the VM code can be translated further by the supplied VM translatorinto Hack assembly code that can then be executed on the supplied CPU Emulator.

A GUI-less, cmd level program


## Operating System
Two OS implementations are supplied: (i) a collection of eight .vm class files, written originally in Jack (just like Unix is written in C), and (ii) a faster implementation of all the OS services, embedded in the supplied VM Emulator.

## Text Comparer
This utility checks if two input text files are identical, up to white space differences. Used in various projects. In Unix use "diff" instead.

A GUI-less, cmd level program

<br><br/><br><br/>

# Running the Software Tools
The supplied software tools are designed to be run from your computer's command-line environment (also known as "terminal", or "shell"). Command-line environments vary from one operating system to another, and working in them requires some knowledge of various OS shell commands.

In order to eliminate this overhead, we supply batch files (for Windows) and scripts (for Unix and Mac OS), developed by Mark Armbrust. These batch and script files enable invoking the supplied nand2tetris tools from the command line on your computer, painlessly. They can be used from any working directory on your computer, without requiring full paths to the files on which they operate. Further, they accept spaces in directory and file names, so they will work if nand2tetris is installed under a directory named, say, "My Documents".
​<br></br>

### **Windows Users**
For the batch files to work from the command line, you must add (once and for all) the nand2tetris/toolsdirectory to your PATH variable.
​
To run a batch file from command-line, type its name, without the .bat extension.

If you use Windows 7 64-bit you need to install the 64-bit version of Java so that 64-bit cmdexe can run Java commands in batch files. If you get the output "'java' is not recognized..." you likely only have the 32-bit Java installed on your computer.

You can create desktop icons and use them to invoke the interactive versions of the following supplied tools: HardwareSimulator, Assembler, CPUEmulator and VMEmulator. This can be done by finding the disk locations of the respective batch files, right-clicking on them and picking "Send to > Desktop." Edit the shortcuts' properties and set "Run" to "minimized."
​<br></br>

## **Usage**
### **Hardware Simulator:** 
To invoke the hardware simulator in interactive mode, type "HardwareSimulator" in the command line. For example:

C:\...\projects\02>HardwareSimulator

(a window will open up, running the interactive version of the Hardware Simulator)

To invoke the hardware simulator in batch (shell/cmd) mode, type "HardwareSimulator" in the command line. For example:

    C:\...\projects\02>HardwareSimulator ALU.tst
*(invokes the simulator, loads the given test script, executes it, and reports the result). Note that the simulator's interactive mode also enables loading and executing test scripts.*

Successful test (example):
    
    C:\...\projects\02>HardwareSimulator ALU.tst
    End of script - Comparison ended successfully

Failed test (example):

    C:\...\projects\02>HardwareSimulator ALU.tst
    Comparison failure at line 24

Error in the associated HDL file:

    C:\...\projects\02>HardwareSimulator ALU.tst
    In HDL file C:\...\projects\02\ALU.hdl, Line 60, out[16]: the specified sub bus is not in the bus range: load ALU.hdl

​

### **CPU Emulator and VM Emulator:** 
These operation of these tools follow the same convention described above. If you invokve either tool without a parameter, the tool will work in interactive mode; if you supply a parameter (test script), the tool will run batch-style.

​

### **Assembler:** 
Typing "Assembler" will start the supplied assembler in interactive mode. Typing "Assembler xxx.asm" will assemble the specified xxx.asm file and generate a file named xxx.hack, containing the translated binary code. Note that the assembler's interactive mode also enables loading and translating .asm files.

Successful assembly (example):

    C:\...\projects\04\fill>Assembler Fill.asm Assembling "c:\...\projects\04\fill\Fill.asm"

Failed assembly (example):

    C:\...\projects\04\fill>Assembler Fill.asm Assembling "C:\...\projects\04\fill\Fill.asm" In line 15, Expression expected

To compare the resulting .hack code file to some expected .hack file, use the supplied TextComparer tool, described below.

​

### **Compiler:** 
Typing "JackCompiler fileName.jack" will compile the supplied Jack file. Typing "JackCompiler directoryName" will compile all the Jack file that are found in the specified directory. Wildcards are not supported. Here are some examples:

Compile the current directory:

    C:\...\projects\09\Reflect>JackCompiler
    Compiling "c:\...\projects\09\Reflect"

Compile a single file:

    C:\...\projects\09\Reflect>JackCompiler Mirrors.jack Compiling "C:\...\projects\09\Reflect\Mirrors.jack"

Compile the "Reflect" directory (for example):

    C:\...\projects\09>JackCompiler Reflect
    Compiling "C:\...\projects\09\Reflect"

​

### **TextComparer:** 
Compares two given files ignoring white space, and reports success or failure. For example, suppose you run the hardware simulator with some test script and get a comparison failure. If you want, you can then use the TextComparer to investigate the problem:

    C:\...\projects\02>HardwareSimulator ALU.tst
    Comparison failure at line 24

    C:\...\projects\02>TextComparer ALU.cmp ALU.out
    Comparison failure in line 23:
    |0101101110100000|0001111011010010|1|1|0|0|0|0|0001111011010010|0|0| |0101101110100000|0001111011010010|1|1|0|0|0|0|0001111011010010|0|1|

*(Note the line number discrepancy between the reports of the two tools).*

​

### **Help:** 
In Windows, each batch file accepts a "/?" option that shows its intended usage. In Mac and Unix, use "-h". For example:

    C:\...\projects\09>JackCompiler /?
    Usage:
    JackCompiler Compiles all the .jack files in the current working directory.
    JackCompiler directoryName Compiles all the .jack files in the specified directory.
    JackCompiler fikeName.jack Compiles the specified Jack file