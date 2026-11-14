<pre align="center">
  <strong>👨‍💻 Bernard Ladenthin</strong> | <a href="https://bernard.ladenthin.net">Homepage</a> | <a href="https://www.linkedin.com/in/bernard-ladenthin-39303b42/">LinkedIn</a>
</pre>

<img src="https://raw.githubusercontent.com/bernardladenthin/bernardladenthin/main/github-metrics.svg" alt="GitHub Metrics" align="right" width="400px" />

**👋 Hey — nice that you want to know more about me.** Based near Berlin, Germany.

I'm a **Senior Site Reliability Engineer** at **Deutsche Bank**: mission-critical financial systems, cloud-native microservices, production reliability at scale — and the analysis of defects that matter for security.

### 🩺 Software Surgery

What I enjoy most is the **smallest possible change to the hardest possible problem**: a fault deep in a large, unfamiliar, sparsely documented system, narrowed down until the fix is a handful of lines — and provable.

**Reproduce** it cheaply → **measure** instead of argue → **halve** it to a standalone reproducer → **change one thing** and show red-to-green → **write down** what turned out to be wrong.

The terrain: binary analysis (disassembly, undocumented formats), emulation, firmware- and boot-level debugging — and **formal verification** where a test cannot be exhaustive. Off the clock: electronics, low-level optimization, small tools between software and hardware, and older architectures (PowerPC, big-endian Unix).

---

### 🧰 Technical Focus

**Java is my primary language**; everything else is picked to reach the layer the problem actually lives on.

| Area | What I work with |
|---|---|
| **Languages** | `Java`, `Kotlin`, `Groovy`, `C`, `C++`, `Python`, `Bash`, `PowerShell`, `SQL`, assembler (x86, PowerPC) |
| **JVM ↔ native** | JNI, FFM, `JNR-FFI`, `OpenCL` from the JVM, `LMDB`, JVM bytecode |
| **Platforms** | Linux, Unix / AIX, Windows, macOS, the BSDs, Android, `WINE`, QEMU/KVM |
| **Performance** | GPU kernels, parallel computing, lock-free concurrency |
| **Crypto & integrity** | `ECC`, `RSA`, `Diffie–Hellman`, Bitcoin, Monero, Bitmessage, `TOR`; error correction (Reed–Solomon, FEC, ECC memory) |
| **Build & release** | Maven, Gradle, Jenkins, GitHub Actions, reproducible and signed releases |
| **Testing & analysis** | TDD, `jqwik`, `ArchUnit`, `PIT` (gated at 100 %), `SpotBugs`, `Error Prone`, `NullAway`, `Checker Framework`, `KUnit`, `KMSAN` |
| **Verification** | `OpenJML`, TLA+ (`TLC`, `Apalache`, `TLAPS`), Java PathFinder, `CBMC`, `jcstress`, `Lincheck`, `vmlens` |

---

### ⚙️ Featured Projects

| Project | What it does |
|---|---|
| 🦙 [**java-llama.cpp**](https://github.com/bernardladenthin/java-llama.cpp) | Java bindings for [llama.cpp](https://github.com/ggml-org/llama.cpp): local LLMs on the JVM — chat, embeddings, reranking, speech synthesis, an OpenAI-compatible server. Natives for Linux, macOS, Windows and Android; `net.ladenthin:llama` on Maven Central. |
| 🧠 [**BitcoinAddressFinder**](https://github.com/bernardladenthin/BitcoinAddressFinder) | JVM + OpenCL tool that generates Bitcoin and altcoin keys at scale and checks them against an `LMDB` address database. |
| 🔄 [**streambuffer**](https://github.com/bernardladenthin/streambuffer) | Thread-safe `OutputStream` → `InputStream` bridge over a dynamic FIFO — verified with OpenJML, TLA+ and Java PathFinder. |
| 🗂️ [**srcmorph**](https://github.com/bernardladenthin/srcmorph) | Prompt-driven source-tree transformer: per-file, per-package and per-project `.ai.md` summaries from a local llama.cpp model; library, CLI and Maven plugin. |

---

### 🔧 Upstream Work

Most of my systems work ends up as patches to other people's projects — open source has interested me since I was a teenager, starting with [openSUSE](https://www.opensuse.org/).

| Project | Contribution | Status |
|---|---|---|
| **[Linux kernel](https://www.kernel.org/)** | `net/sched`: `em_text` dumped kernel stack, pointers included, to userspace — KASLR readable dump by dump; fixed with `= {}` | ✅ [`9c572a83037a`](https://git.kernel.org/linus/9c572a83037a), Linux 7.3, [CVE-2026-98584](https://www.cve.org/CVERecord?id=CVE-2026-98584) |
| **[Apalache](https://github.com/apalache-mc/apalache)** | TLA+ model checker: `\E x \in a..b` over an empty range silently cut executions — missed violations reported as `NoError` | ✅ [#3505](https://github.com/apalache-mc/apalache/pull/3505) ([#3503](https://github.com/apalache-mc/apalache/issues/3503)) |
| **[sccache](https://github.com/mozilla/sccache)** | nvcc / distributed-compile exit codes misreported as signals | ✅ [#2932](https://github.com/mozilla/sccache/pull/2932), sccache 0.19.0 |
| **[llama.cpp](https://github.com/ggml-org/llama.cpp)** | NEON fp32→fp16 conversion, s390x repack guard, per-request reasoning budget | ✅ [#30505](https://github.com/ggml-org/llama.cpp/pull/30505), [#28775](https://github.com/ggml-org/llama.cpp/pull/28775), [#23116](https://github.com/ggml-org/llama.cpp/pull/23116) |
| **[OpenJML](https://github.com/OpenJML/OpenJML)** | specs and tests for `Atomic*`; runtime-assertion-checking defects reported with reproducers, fixed by the maintainer | ✅ [#982](https://github.com/OpenJML/OpenJML/pull/982), [Specs #29](https://github.com/OpenJML/Specs/pull/29), [#1012](https://github.com/OpenJML/OpenJML/issues/1012), [#1050](https://github.com/OpenJML/OpenJML/issues/1050) |
| **[VeraCrypt](https://www.veracrypt.fr/)** | tests for the crypto and platform layers, alignment, build and portability fixes | ✅ [#1843](https://github.com/veracrypt/VeraCrypt/pull/1843), [#1842](https://github.com/veracrypt/VeraCrypt/pull/1842), [#1844](https://github.com/veracrypt/VeraCrypt/pull/1844), [#1525](https://github.com/veracrypt/VeraCrypt/pull/1525), [#1526](https://github.com/veracrypt/VeraCrypt/pull/1526) · 🔄 [#1850](https://github.com/veracrypt/VeraCrypt/pull/1850), [#1923](https://github.com/veracrypt/VeraCrypt/pull/1923) |
| **[hashcat](https://hashcat.net/hashcat/)** | secp256k1: zero-scalar out-of-bounds read, zero-input hang, safegcd inverse | ✅ [#4763](https://github.com/hashcat/hashcat/pull/4763), [#2706](https://github.com/hashcat/hashcat/pull/2706) |
| **[subprocess.h](https://github.com/sheredom/subprocess.h)** | portability: AIX, older glibc and compilers, Windows pointer widths, pipe ends off the standard descriptors, a portability workflow | ✅ [#104](https://github.com/sheredom/subprocess.h/pull/104), [#105](https://github.com/sheredom/subprocess.h/pull/105), [#106](https://github.com/sheredom/subprocess.h/pull/106), [#112](https://github.com/sheredom/subprocess.h/pull/112), [#113](https://github.com/sheredom/subprocess.h/pull/113), [#117](https://github.com/sheredom/subprocess.h/pull/117), [#118](https://github.com/sheredom/subprocess.h/pull/118) |
| **[utest.h](https://github.com/sheredom/utest.h)** | portability: AIX, 32-bit builds under `-Wpedantic`, missing `PRI` macros, a test filter dropping tests, a portability workflow | ✅ [#188](https://github.com/sheredom/utest.h/pull/188), [#189](https://github.com/sheredom/utest.h/pull/189), [#190](https://github.com/sheredom/utest.h/pull/190), [#191](https://github.com/sheredom/utest.h/pull/191), [#192](https://github.com/sheredom/utest.h/pull/192) |
| **[QEMU](https://www.qemu.org/)** | PowerPC / `pseries`: 14 defects, each with a bare-metal assembly reproducer — e.g. `spapr_vscsi` silently corrupting transfers above 128 KiB | 🔄 first patch series on qemu-devel |
| **[GCC](https://gcc.gnu.org/)** | AIX / rs6000: EH frame tables in `collect2` ([PR60939](https://gcc.gnu.org/PR60939)), call-site return PC past the TOC restore ([PR107909](https://gcc.gnu.org/PR107909)) | 🔄 on gcc-patches |
| **[Java PathFinder](https://github.com/javapathfinder/jpf-core)** | `AtomicLong` native-peer model; lambda type names colliding with anonymous classes | 🔄 [#664](https://github.com/javapathfinder/jpf-core/pull/664), [#665](https://github.com/javapathfinder/jpf-core/pull/665) |
| **[lmdbjava](https://github.com/lmdbjava/lmdbjava)** | Netty `ByteBuf` buffers, reverse-prefix iteration, close-during-read lifecycle | 🔄 [#290](https://github.com/lmdbjava/lmdbjava/pull/290), [#291](https://github.com/lmdbjava/lmdbjava/pull/291), [#292](https://github.com/lmdbjava/lmdbjava/pull/292); [#288](https://github.com/lmdbjava/lmdbjava/pull/288) and [#294](https://github.com/lmdbjava/lmdbjava/pull/294) taken into [#293](https://github.com/lmdbjava/lmdbjava/pull/293) |
| **[JeroMQ](https://github.com/zeromq/jeromq)** | `Poller`: cancelled keys flushed before registering handles — a connect hand-off race | 🔄 [#1022](https://github.com/zeromq/jeromq/pull/1022) |
| **[kotlinx.serialization](https://github.com/Kotlin/kotlinx.serialization)** | `Int` overflow when growing array buffers | 🔄 [#2985](https://github.com/Kotlin/kotlinx.serialization/pull/2985) |
| **[Jenkins script-security](https://github.com/jenkinsci/script-security-plugin)** | whitelist the harmless `java.time` factory and conversion methods | 🔄 [#909](https://github.com/jenkinsci/script-security-plugin/pull/909) |
| **[smartmontools](https://github.com/smartmontools/smartmontools)** | SanDisk Extreme Portable SSD: vendor log pages, replay of SCSI traces for tests | 🔄 [#672](https://github.com/smartmontools/smartmontools/pull/672) |
| **[Wine](https://www.winehq.org/)** | `oleaut32`: `OleIconToCursor` stub; `browseui`: `ClassFactory_LockServer` | ✅ [`26f29fda`](https://gitlab.winehq.org/wine/wine/-/commit/26f29fda), [`db07476c`](https://gitlab.winehq.org/wine/wine/-/commit/db07476c), [`57c8c9e5`](https://gitlab.winehq.org/wine/wine/-/commit/57c8c9e5) (2006/07) |
| **[linux-dash](https://github.com/tariqbuilds/linux-dash)** | chart scale: CPU load maximum always 100 | ✅ [#293](https://github.com/tariqbuilds/linux-dash/pull/293) (2015) |
| **[geotools](https://github.com/geotools/geotools)** | JDOM update to 1.1.3 | ✅ [#223](https://github.com/geotools/geotools/pull/223) (2013) |

✅ merged · 🔄 in review

---

### 🚗 Before SRE

Over a decade at **IAV GmbH** as a **Senior Software Developer** in automotive infotainment and HMI: Android-based HMI (AOSP), embedded and protocol-level work, system integration, CI/CD and test automation under ASPICE. Guest lecturer on DevOps and continuous delivery in automotive software; certified for work on high-voltage automotive systems (DGUV-I 209-093); certified first aider.
