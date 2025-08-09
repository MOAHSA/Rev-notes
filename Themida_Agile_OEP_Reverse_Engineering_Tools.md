# Themida Reverse Engineering Tools and Resources

## Tools Used in the Challenges

### .NET & Agile Obfuscation Tools
- **AgileDotNetSlayer**  
  Used for deobfuscating Agile .NET obfuscated binaries and strings.

- **ILSpy**  
  Open-source .NET assembly browser and decompiler.

- **Detect It Easy (DIE)**  
  Tool for binary file analysis and packer detection.

### Themida Unpacking and Debugging Tools
- **Themida-Unpacker-for-.NET**  
  Specialized unpacker for Themida packed .NET binaries.

- **x32dbg / x64dbg**  
  Popular Windows debuggers for 32-bit and 64-bit binaries, respectively.

- **Scylla / ScyllaHide**  
  Scylla: IAT (Import Address Table) rebuilding tool for dumped binaries.  
  ScyllaHide: Anti-anti-debug plugin for debuggers.

- **Unlicense**  
  Dynamic unpacker tool using Frida, supports Themida/WinLicense protected binaries.

- **TinyTracer**  
  Tool for tracing execution to find Original Entry Point (OEP).

- **HollowsHunter**  
  Tool for detecting hollowed processes and reconstructing Import Address Table.

### Additional Tools / Libraries
- **Python with PyCryptodome**  
  For AES decryption and base64 decoding.

- **John the Ripper**  
  Password cracker used to brute-force archive passwords.

- **PE-Bear**  
  Portable Executable file inspection tool.

- **IDA Pro**  
  Interactive Disassembler, used for static analysis and reverse engineering.

---

## Resources

- Full writeup available at: [Themida Reverse Fun by Saud Smadi](https://www.smadi0x86.tech/posts/themida-reverse-fun/1)

---

## Key Terms

- **OEP (Original Entry Point)**  
  The original address where the program starts executing, restored after unpacking.

- **Themida**  
  A commercial packer/protector software designed to prevent reverse engineering and tampering.

- **Agile .NET Obfuscator**  
  A .NET obfuscation tool that makes decompilation and analysis more difficult.

---

