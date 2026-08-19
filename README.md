<pre align="center">
  <strong>👨‍💻 Bernard Ladenthin</strong> | <a href="https://bernard.ladenthin.net">Homepage</a> | <a href="https://www.linkedin.com/in/bernard-ladenthin-39303b42/">LinkedIn</a>
</pre>

<img src="https://raw.githubusercontent.com/bernardladenthin/bernardladenthin/main/github-metrics.svg" alt="GitHub Metrics" align="right" width="400px" />

**👋 Hey — nice that you want to know more about me.**  
**🌍 Based near Berlin, Germany.**

I'm a **Senior Site Reliability Engineer** at **Deutsche Bank**, focused on stabilizing mission-critical financial systems, cloud-native microservices, and production reliability at scale. Different domain, same discipline as everything below.

---

### 🩺 Software Surgery — the work I enjoy most

What I like best is the **smallest possible change to the hardest possible problem**: a fault buried deep in a large, unfamiliar, sparsely documented system — narrowed down until the fix is a handful of lines, and provable.

The loop rarely changes, and every pass is meant to make the next one cheaper:

- **Reproduce it**, then make the reproduction cheap enough to run again and again
- **Measure instead of argue** — a plausible theory that survives an hour of reasoning still dies in one experiment
- **Halve the problem** until what remains is a minimal, standalone reproducer
- **Change exactly one thing**, and show the red-to-green transition
- **Write down what turned out to be wrong**, not just what turned out to be right

The terrain is usually the same, and it is why the method has to be this literal-minded: **binary analysis** — disassembly, undocumented file and data formats — **emulation**, and **firmware- and boot-level debugging**. Systems with neither source nor documentation to read, where the only honest answer comes from measuring the difference between a run that works and a run that does not.

**📡 Off the clock** — the same interests turn into electronics projects, low-level optimization, and small utilities and microtools that sit between software and hardware. Older and less common architectures and AIX/Unix systems fascinate me, and I'm still learning my way around them.

---

### 🧰 Technical Focus

**Java is my primary language.** Everything else on this list is picked to reach whichever layer the problem actually lives on — and interesting problems rarely stay on one.

| Layer | What I work with |
|---|---|
| **Application / JVM** | `Java` (primary), `Kotlin`, `Groovy` — Maven Central libraries, CLI tools, services |
| **Between the layers** | JNI and native bindings, `JNR-FFI`, `OpenCL` from the JVM, memory-mapped storage (`LMDB`), stream and process plumbing, JVM bytecode |
| **Systems / native** | `C`, `C++`, POSIX, cross-platform portability across Linux, macOS, Windows, the BSDs and AIX |
| **Low level** | `Assembler` (x86, PowerPC), disassembly |

Cutting across every layer:

| Area | What I work with |
|---|---|
| **Scripting & glue** | `Python`, `Bash`, `PowerShell` |
| **OS & systems** | `GNU/Linux`, `Unix` / `AIX`, `Windows`, `WINE`, QEMU/KVM |
| **Data & integrity** | `SQL`, `LMDB` key–value store, error correction (`ECC` memory, `FEC`, Reed–Solomon) |
| **Performance** | high-performance and parallel computing — `OpenCL`, GPU kernels, lock-free concurrency |
| **Cryptography** | elliptic curves (`ECC`), `RSA`, `Diffie–Hellman`, blockchain (`Bitcoin`, `Monero`, `Bitmessage`) |
| **Build & DevOps** | `Maven`, `Gradle`, `Ant`, `Jenkins`, GitHub Actions, reproducible releases & artifact signing |
| **Privacy & security** | `TOR`, secure communication, blockchain privacy, attack-vector analysis |

**🧪 Quality & testing** — the part I am most opinionated about. Test-driven development, and then everything that can be made to fail a build:

| Kind | What I use |
|---|---|
| **Property-based & architecture tests** | `jqwik`, `ArchUnit` |
| **Mutation testing & coverage** | `PIT` (gated at 100%), `JaCoCo` |
| **Static analysis & null safety** | `SpotBugs`, `Error Prone`, `NullAway`, `Checker Framework`, `JSpecify` |
| **Concurrency verification** | `jcstress`, `Lincheck`, `vmlens` |

---

### ⚙️ Featured Projects

| Project | What it does |
|---|---|
| 🧠 [**BitcoinAddressFinder**](https://github.com/bernardladenthin/BitcoinAddressFinder) | High-performance JVM + OpenCL tool that generates and checks Bitcoin and altcoin addresses at scale, built for cryptographic experiments and raw key-search throughput — parallel EC key generation, vanity-address search, fast `LMDB` lookups. |
| 🔄 [**streambuffer**](https://github.com/bernardladenthin/streambuffer) | Thread-safe buffer connecting an `OutputStream` to an `InputStream` for real-time data flow between threads: concurrent reads and writes, automatic buffer trimming, optional clone-on-write safety. |
| 🦙 [**java-llama.cpp**](https://github.com/bernardladenthin/java-llama.cpp) | Java bindings for [llama.cpp](https://github.com/ggml-org/llama.cpp) that run local LLMs entirely on the JVM — text and chat completion, embeddings, reranking, infilling, no cloud dependency. Pre-built native binaries for Linux, macOS, Windows and Android; on Maven Central as `net.ladenthin:llama`. |
| 🗂️ [**srcmorph**](https://github.com/bernardladenthin/srcmorph) | Prompt-driven source-tree transformer that documents and reshapes Java projects with a local llama.cpp model, no cloud required. Walks the tree through configurable prompts, emits layered per-file, per-package and per-project `.ai.md` summaries, and updates only what changed. 3-module Maven reactor: core (`net.ladenthin:srcmorph`), CLI (`net.ladenthin:srcmorph-cli`), Maven plugin (`net.ladenthin:srcmorph-maven-plugin`). |

---

### 🔧 Upstream Work

Most of my systems work ends up as patches to other people's projects. The most complex of those is **[QEMU](https://www.qemu.org/)** — defects in the PowerPC / `pseries` emulation, found while getting AIX 5.3, an operating system from 2004, to install and boot under it. Each one ships with a standalone assembly reproducer that runs bare-metal in seconds and needs no guest OS at all, so a defect can be shown to someone who has never heard of AIX. Several are not AIX-specific: a 16-bit descriptor offset in `spapr_vscsi` that silently corrupts guest data on transfers above 128 KiB, a standard INQUIRY vendor area returned all-zero to every SCSI guest, and `slbmte` / `slbie` disagreeing about what 32-bit mode means. The individual fixes run to a few lines each; the work was in the measuring.

Open source has interested me since I was a teenager — it started with [openSUSE](https://www.opensuse.org/). Some of the other projects I have contributed to over the years:

- [VeraCrypt](https://www.veracrypt.fr/)
- [subprocess.h](https://github.com/sheredom/subprocess.h)
- [utest.h](https://github.com/sheredom/utest.h)
- [llama.cpp](https://github.com/ggml-org/llama.cpp)
- [Wine](https://www.winehq.org/)
- [hashcat](https://hashcat.net/hashcat/)
- [Linux kernel](https://www.kernel.org/)

---

### ✅ Certifications & Qualifications

- ⚡ Certified for working on high-voltage automotive systems (up to 1000 V AC / 1500 V DC):  
  Elektrofachkraft (EFffT) gem. DGUV-I 209-093 – Stufe 2E (FHV)
- 🩹 Certified first aider  
- 🎓 Guest lecturer on DevOps and continuous delivery in automotive software

---

### 🚗 Automotive Background (IAV GmbH) — past work

Before moving to SRE work, I spent over a decade at **IAV GmbH** as a **Senior Software Developer**, building automotive infotainment and HMI software — the user-facing systems drivers interact with. That covered Android-based HMI development (AOSP), embedded and protocol-level work, interface design and system integration, CI/CD pipelines and test automation, performance optimization, and ASPICE process and quality standards.
