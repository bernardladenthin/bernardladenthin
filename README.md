<pre align="center">
  <strong>👨‍💻 Bernard Ladenthin</strong> | <a href="https://bernard.ladenthin.net">Homepage</a> | <a href="https://www.linkedin.com/in/bernard-ladenthin-39303b42/">LinkedIn</a>
</pre>

<img src="https://raw.githubusercontent.com/bernardladenthin/bernardladenthin/main/github-metrics.svg" alt="GitHub Metrics" align="right" width="400px" />

**👋 Hey — nice that you want to know more about me.**  
**🌍 Based near Berlin, Germany.**

I'm a **Senior Site Reliability Engineer** at **Deutsche Bank**, focused on stabilizing mission-critical financial systems, cloud-native microservices, production reliability at scale — and on the analysis of defects that matter for security. Different domain, same discipline as everything below.

---

### 🩺 Software Surgery — the work I enjoy most

What I like best is the **smallest possible change to the hardest possible problem**: a fault buried deep in a large, unfamiliar, sparsely documented system — narrowed down until the fix is a handful of lines, and provable.

The loop rarely changes, and every pass is meant to make the next one cheaper:

- **Reproduce it**, then make the reproduction cheap enough to run again and again
- **Measure instead of argue** — a plausible theory that survives an hour of reasoning still dies in one experiment
- **Halve the problem** until what remains is a minimal, standalone reproducer
- **Change exactly one thing**, and show the red-to-green transition
- **Write down what turned out to be wrong**, not just what turned out to be right

The terrain is usually the same, and it is why the method has to be this literal-minded: **binary analysis** — disassembly, undocumented file and data formats — **emulation**, and **firmware- and boot-level debugging**. Systems with neither source nor documentation to read, where the only honest answer comes from measuring the difference between a run that works and a run that does not. And where a test cannot be exhaustive, **formal verification** takes over from measurement.

**📡 Off the clock** — the same interests turn into electronics projects, low-level optimization, and small utilities and microtools that sit between software and hardware, plus older architectures (PowerPC, big-endian Unix) and the firmware underneath them.

---

### 🛡️ Security

**Linux kernel, `net/sched` — CVE-2026-98584.** The traffic-classifier ematch `em_text` copied a partially uninitialised on-stack `struct tcf_em_text` to userspace on every dump. The residue is kernel stack — pointers included — handed to any process allowed to read the qdisc configuration, so KASLR could be read out systematically, dump by dump. Found by systematic analysis of the netlink dump paths, narrowed to the one struct, then shown with a standalone reproducer; a KMSAN run only confirmed what the analysis had predicted. The fix is a single line: two braces, `= {}`. Upstream in **Linux 7.3**.

[commit `9c572a83037a`](https://git.kernel.org/linus/9c572a83037a) · [CVE record](https://www.cve.org/CVERecord?id=CVE-2026-98584)

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
| **Kernel & C** | `KUnit`, `checkpatch`, `KMSAN` and the other sanitizers, `CBMC` counterexamples |

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

Most of my systems work ends up as patches to other people's projects. The most complex set is for **[QEMU](https://www.qemu.org/)**: defects in the PowerPC / `pseries` emulation, each shipped with a standalone assembly reproducer that runs bare-metal in seconds and needs no guest OS. Several affect every guest — a 16-bit descriptor offset in `spapr_vscsi` that silently corrupts data on transfers above 128 KiB, an INQUIRY vendor area returned all-zero to every SCSI guest, `slbmte` / `slbie` disagreeing about 32-bit mode. The fixes run to a few lines each; the work was in the measuring.

Open source has interested me since I was a teenager — it started with [openSUSE](https://www.opensuse.org/). Merged contributions, newest first:

- **[Linux kernel](https://www.kernel.org/)** — [`9c572a83037a`](https://git.kernel.org/linus/9c572a83037a) `net/sched`: stack infoleak in `em_text_dump()` (CVE-2026-98584, Linux 7.3)
- **[sccache](https://github.com/mozilla/sccache)** — [#2932](https://github.com/mozilla/sccache/pull/2932) nvcc / distributed-compile exit codes misreported as signals (released in 0.19.0)
- **[llama.cpp](https://github.com/ggml-org/llama.cpp)** — [#30505](https://github.com/ggml-org/llama.cpp/pull/30505), [#28775](https://github.com/ggml-org/llama.cpp/pull/28775), [#23116](https://github.com/ggml-org/llama.cpp/pull/23116)
- **[VeraCrypt](https://www.veracrypt.fr/)** — [#1843](https://github.com/veracrypt/VeraCrypt/pull/1843), [#1842](https://github.com/veracrypt/VeraCrypt/pull/1842), [#1844](https://github.com/veracrypt/VeraCrypt/pull/1844), [#1525](https://github.com/veracrypt/VeraCrypt/pull/1525), [#1526](https://github.com/veracrypt/VeraCrypt/pull/1526) — tests for the crypto and platform layers, build and portability fixes
- **[OpenJML](https://github.com/OpenJML/OpenJML)** — [#982](https://github.com/OpenJML/OpenJML/pull/982), [Specs #29](https://github.com/OpenJML/Specs/pull/29); runtime-assertion-checking defects [#1012](https://github.com/OpenJML/OpenJML/issues/1012) and [#1050](https://github.com/OpenJML/OpenJML/issues/1050) reported with reproducers, fixed by the maintainer
- **[lmdbjava](https://github.com/lmdbjava/lmdbjava)** — [#288](https://github.com/lmdbjava/lmdbjava/pull/288)
- **[hashcat](https://hashcat.net/hashcat/)** — [#4763](https://github.com/hashcat/hashcat/pull/4763), [#2706](https://github.com/hashcat/hashcat/pull/2706)
- **[subprocess.h](https://github.com/sheredom/subprocess.h)** — 7 pull requests ([#104](https://github.com/sheredom/subprocess.h/pull/104) … [#118](https://github.com/sheredom/subprocess.h/pull/118)), **[utest.h](https://github.com/sheredom/utest.h)** — 5 ([#188](https://github.com/sheredom/utest.h/pull/188) … [#192](https://github.com/sheredom/utest.h/pull/192))
- **[Wine](https://www.winehq.org/)** — three patches, 2006/2007
- Older: [linux-dash #293](https://github.com/tariqbuilds/linux-dash/pull/293), [geotools #223](https://github.com/geotools/geotools/pull/223)

---

### 🚗 Automotive Background (IAV GmbH) — past work

Before moving to SRE work, I spent over a decade at **IAV GmbH** as a **Senior Software Developer**, building automotive infotainment and HMI software: Android-based HMI (AOSP), embedded and protocol-level work, system integration, CI/CD and test automation under ASPICE.

**Additional qualifications:** guest lecturer on DevOps and continuous delivery in automotive software; certified for work on high-voltage automotive systems (Elektrofachkraft für festgelegte Tätigkeiten, DGUV-I 209-093); certified first aider.
