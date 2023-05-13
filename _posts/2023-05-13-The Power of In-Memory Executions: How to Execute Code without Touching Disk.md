---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "The Power of In-Memory Executions: How to Execute Code without Touching Disk"
date:   2023-05-13 16:50:10 +1000
categories:
  - Red Team
  - AV Bypass
  - Security Automation
tags:
  - AV Bypass
  - In Memory Execution
---
In-memory execution is a technique used by malware developers to evade detection by traditional antivirus solutions. Instead of writing their malicious code to disk, they inject it directly into memory, making it much harder to detect and analyse. In this blog post, we will explore in-memory execution techniques using various programming languages and file formats, including C#, object files, rDLLs, shellcode, and PowerShell. <BR>
  
**C# In-memory Execution:**

C# is a popular programming language for building Windows applications. However, it can also be used for malicious purposes. One technique used by malware developers is to compile their C# code into an assembly, which can be loaded directly into memory using the Assembly.Load method. Once loaded, the malicious code can be executed without ever touching the disk.

Here's an example of how this can be done: 

![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/bdf18f4a-c62a-465c-b812-d000bb0b1af0)

 Above code loads a malicious assembly into memory and then executes it. The first step is to load the assembly into memory. This is done using the Assembly.Load() method. The Assembly.Load() method takes a byte array as input. The byte array contains the contents of the assembly. In this case, the byte array is loaded from the file C:\malware.dll.

Once the assembly is loaded into memory, the next step is to execute it. This is done using the InvokeMember() method. The InvokeMember() method takes a number of parameters. The first parameter is the name of the method to execute. In this case, the method to execute is called Execute. The second parameter is the binding flags. The binding flags specify how the method is to be executed. In this case, the binding flags are set to BindingFlags.InvokeMethod. The third parameter is the culture. The culture is not used in this case, so it is set to null. The fourth parameter is the instance of the object on which the method is to be executed. In this case, the instance is null. The fifth parameter is the arguments to the method. In this case, there are no arguments, so the fifth parameter is also set to null.

When the InvokeMember() method is called, it will execute the Execute method on the malicious assembly. The Execute method will then do whatever it is designed to do. This could be anything from stealing data to crashing the system.

It is important to note that this code is just an example. The actual code that an attacker would use to execute malicious code would be much more sophisticated. However, this code provides a basic overview of how in-memory executions work. <BR>

**Object File In-memory Execution:**

An object file is a binary file containing compiled code and data that can be linked with other object files to create an executable program. Object files can be loaded directly into memory using the Windows API function LoadLibrary. Once loaded, the code can be executed using the GetProcAddress function to obtain a function pointer.

Here's an example of how this can be done: 

![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/21b796b0-8019-4f9e-ae48-1583247c101b)

 The first step is to load the object file into memory using the LoadLibrary function. This function takes the name of the object file as its argument and returns a handle to the loaded library. Once the object file is loaded, the code can be executed using the GetProcAddress function. This function takes the handle to the loaded library and the name of the function to execute as its arguments and returns a pointer to the function. The function pointer can then be used to call the function.

This code will load the object file malware.obj into memory, get the address of the function MalwareFunction, and then call the function. The function MalwareFunction will be executed in the context of the current thread.<BR>
  
**rDLL In-memory Execution:**

rDLL (Reflective Dynamic Link Library) is a technique for loading a DLL directly into memory without using the LoadLibrary function. Instead, the DLL is mapped into memory using the VirtualAlloc function and then initialised using a reflective loader.

Here's an example of how this can be done using the ReflectiveLoader library: 

![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/ba0b48ec-50d5-4bda-bb1e-04010fb5816b)

 The first line includes the Windows.h header file, which provides access to Windows API functions and data types. The second line includes the ReflectiveLoader.h header file, which contains the necessary definitions for the reflective DLL loader. In the main function, the ReflectiveLoader function is called with the malware.dll to be loaded as the first argument and a null value for the second argument. The ReflectiveLoader function loads the DLL into memory, resolves its dependencies, and returns a pointer to the base address of the loaded module.

The GetProcAddress function is called to get the address of the malicious function named MalwareFunction in the loaded module. GetProcAddress is a Windows API function that returns the address of a function or variable in a dynamic-link library (DLL) module. The address of the malicious function is stored in a FARPROC variable named func. Finally, the malicious function is executed by casting the func variable to a function pointer and calling it. <BR>
  
**Shellcode In-memory Execution:**

Shellcode is a small piece of code that is injected into a target process to execute a payload. It is often used by attackers to bypass antivirus detection and gain remote access to a system. Shellcode can be executed in-memory by allocating executable memory using the VirtualAlloc function and copying the shellcode into the allocated memory. The code can then be executed using a function pointer.

Here's an example of how this can be done: 

![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/900b5509-35ee-4fb3-b95e-0e9a13a96297)

 After including the Windows header file the main function starts, which is the entry point for the program.

In main function we allocate memory for the shellcode. The VirtualAlloc function takes four parameters:

    A pointer to a variable that will be used to store the address of the allocated memory.
    The size of the memory to allocate.
    The memory protection flags.
    The desired alignment of the memory.

The memory protection flags determine how the allocated memory can be used. In this case, we want to be able to execute the code in the allocated memory, so we will use the PAGE_EXECUTE flag.

The memcpy function copies the shellcode into the allocated memory. The memcpy function takes three parameters:

    A pointer to the destination buffer.
    A pointer to the source buffer.
    The number of bytes to copy.

Last line executes the shellcode. The cast operator converts the address of the allocated memory to a pointer to a function. The parentheses around the address call the function. <BR>
  
**PowerShell In-memory Execution:**

PowerShell is a powerful scripting language that is built into Windows. It can be used to automate administrative tasks or to execute malicious code. PowerShell scripts can be executed in-memory by loading the script into a byte array and using the Invoke-Expression cmdlet to execute the script.

Here's an example of how this can be done: 

![image](https://github.com/Viralmaniar/viralmaniar.github.io/assets/3501170/720b6b3e-ef6e-47cc-b36a-8cd63f92686f)

 The above PowerShell code demonstrates an in-memory execution technique by loading a script file named "malware.ps1" into memory and executing it without writing it to disk. The first line of the code reads all the bytes from the script file and stores them in a byte array named $bytes. The second line converts the byte array to a string using the Unicode encoding and stores the result in a variable named $script. Finally, the Invoke-Expression cmdlet is used to execute the script stored in the $script variable in memory. This technique can be used by attackers to evade detection by traditional antivirus solutions, as the script is never written to disk.
<BR>
  
**Conclusion:**

In-memory execution is a technique used by malware developers to evade detection by traditional antivirus solutions. Here we have explored various in-memory execution techniques using different languages and file formats, including C#, object files, rDLLs, shellcode, and PowerShell. By understanding how these techniques work, cyber defenders can better protect against attacks and keep their systems and data safe. It is important to keep up to date with the latest threats and techniques and to implement appropriate security measures to protect against them.

I hope this post provided you with new insights on in-memory execution techniques. If you found this post helpful, please consider sharing it with others who might benefit from this knowledge. Please let me know if you have any questions. 

For more content follow me on Twitter - @ManiarViral or on LinkedIn - https://www.linkedin.com/in/viralmaniar/. 

