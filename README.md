<pre align="center">
  <strong>👨‍💻 Bernard Ladenthin</strong> | <a href="http://bernard.ladenthin.net">Homepage</a> | <a href="https://www.linkedin.com/in/bernard-ladenthin-39303b42/">LinkedIn</a>
</pre>

<img src="https://raw.githubusercontent.com/bernardladenthin/bernardladenthin/main/github-metrics.svg" alt="GitHub Metrics" align="right" width="400px" />

I'm a **Senior L3 Site Reliability Engineer** at **Deutsche Bank** in Berlin, focused on **stabilizing mission-critical financial systems**, **cloud-native microservices**, and **production reliability at scale**.

---

### 🩺 Software Surgery — the work I enjoy most

What I like best is the **smallest possible change to the hardest possible problem**: a fault buried deep in a large, unfamiliar, sparsely documented system — narrowed down until the fix is a handful of lines, and provable.

The method rarely changes:

- **Reproduce it**, then make the reproduction cheap enough to run again and again
- **Measure instead of argue** — a plausible theory that survives an hour of reasoning still dies in one experiment
- **Halve the problem** until what remains is a minimal, standalone reproducer
- **Change exactly one thing**, and show the red-to-green transition
- **Write down what turned out to be wrong**, not just what turned out to be right

A recent example: AIX 5.3 — an operating system from 2004 — would not install under QEMU's `pseries` emulation. Two causes, found by measurement rather than by reading code. One was a stale 32-bit half of a register that the emulator folded into a segment identifier, corrupting the address space of every shared library; **three lines**. The other was a device-tree property that was simply never published, so the installer chose the wrong kernel and the finished system crashed on its first boot; **one line, and the property is empty — zero bytes would have done**.

Both ship with an assembly reproducer that runs bare-metal in six seconds and needs no operating system at all, so the defect can be shown to someone who has never heard of AIX.

---

### 🧰 Technical Focus
- **JVM:** `Java`, `Kotlin`, `Groovy`
- **High-level:** `C++`, `.NET`, `PHP`
- **Scripting:** `Python`
- **Low-level:** `Assembler (x86, Java bytecode)`, `C`
- **OS & systems:** `GNU/Linux`, `LAMP`, `WINE`
- **Databases & data integrity:** `MySQL`, `SQL`, `LMDB` key–value store, error correction (`ECC`, `FEC`, `RS-Codes`)
- **Performance:** high-performance and parallel computing (`OpenCL`, `VHDL`)
- **Cryptography:** `ECC`, `RSA`, `Diffie–Hellman`, blockchain (`Bitcoin`, `Monero`, `Bitmessage`)
- **Build & DevOps:** `Maven`, `Ant`, `Gradle`, `Jenkins`
- **Privacy & security:** `TOR`, secure communication, blockchain privacy, attack-vector analysis

---

### 🔬 Reverse Engineering & Low-Level Debugging

- **Binary analysis** — disassembly, undocumented file and data formats
- **Emulation, firmware and boot-level debugging**
- **Differential debugging** — narrowing a fault down by measuring
  the difference, then reducing it to a minimal reproducer

---

### 🧪 Quality & Testing

I care deeply about well-tested software with strong quality assurance. Across my projects I combine test-driven development with:

- Property-based testing (`jqwik`) and architecture tests (`ArchUnit`)
- Mutation testing (`PIT`) and code coverage (`JaCoCo`)
- Static analysis and null safety (`SpotBugs`, `Error Prone`, `NullAway`)
- Concurrency verification (`jcstress`, `Lincheck`, `vmlens`)

---

### 🛠️ Professional Areas

- Automotive infotainment & HMI software development
- Software integration and interface design
- Embedded development and protocol-level work
- DevOps and continuous delivery for infotainment systems
- Guest lecturer on CI/CD in automotive software

---

### 🚗 Automotive Background (IAV GmbH)

I spent over a decade at **IAV GmbH** as a **Senior Software Developer**, building **complex automotive infotainment and HMI (Human-Machine Interface) solutions** — the rich, user-facing software that drivers interact with. My focus areas:

- Android-based HMI development (AOSP)
- CI/CD pipelines and test automation
- Performance optimization and system integration
- Process & quality standards (ASPICE)

---

### ✅ Certifications & Qualifications

- ⚡ Certified for working on high-voltage automotive systems (up to 1000 V AC / 1500 V DC):  
  Elektrofachkraft (EFffT) gem. DGUV-I 209-093 – Stufe 2E (FHV)
- 🩹 Certified first aider  
- 🎓 Guest lecturer on DevOps and continuous delivery in automotive software

---

### ⚙️ Featured Projects

#### 🧠 [BitcoinAddressFinder](https://github.com/bernardladenthin/BitcoinAddressFinder)
A high-performance JVM + OpenCL tool that generates and checks Bitcoin and altcoin addresses at scale. Built for cryptographic experiments and raw key-search throughput — with parallel EC key generation, vanity-address search, and fast LMDB lookups.

#### 🔄 [streambuffer](https://github.com/bernardladenthin/streambuffer)
A thread-safe buffer that connects an `OutputStream` to an `InputStream` for real-time data flow between threads. Supports concurrent reads and writes, automatic buffer trimming, and optional clone-on-write safety.

#### 🦙 [java-llama.cpp](https://github.com/bernardladenthin/java-llama.cpp)
Java bindings for [llama.cpp](https://github.com/ggerganov/llama.cpp) that run local LLMs entirely on the JVM — text and chat completion, embeddings, reranking, and infilling, with no cloud dependency. Ships pre-built native binaries for Linux, macOS, Windows, and Android. Published on Maven Central as `net.ladenthin:llama`.

#### 🗂️ [srcmorph](https://github.com/bernardladenthin/srcmorph)
A prompt-driven source-tree transformer that documents and reshapes Java projects with a local llama.cpp model — no cloud required. Walks a source tree and processes each file through configurable prompts, emitting layered per-file, per-package, and per-project `.ai.md` summaries; updates only the files that changed. Ships as a 3-module Maven reactor — a framework-free core library (`net.ladenthin:srcmorph`), a standalone CLI (`net.ladenthin:srcmorph-cli`), and a Maven plugin (`net.ladenthin:srcmorph-maven-plugin`).

---

### 📡 Personal Interests

I love working on **electronics projects** and experimenting with **low-level optimization techniques**.  
In my spare time, I craft utilities and microtools that blend software and hardware.

I like figuring out how systems behave when there is neither source nor documentation — binary analysis, emulation, and boot-level debugging. Older and less common architectures and AIX/Unix systems fascinate me, and I'm still learning my way around them.

---

### 🌍 Location

Based near **Berlin, Germany**, I'm passionate about well-tested, efficient, and secure software — whether it's running on a car, a GPU, or a tiny embedded chip.

---

> Feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/bernard-ladenthin-39303b42/).  
> I'm always happy to talk about tech, performance, or embedded systems!
