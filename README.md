# ToughLad — systems & performance

> I ship low-latency services, make code cheaper, and **own the tail**.

<div align="center">

[![Rust](https://img.shields.io/badge/Rust-000?logo=rust)](https://www.rust-lang.org/)
[![Go](https://img.shields.io/badge/Go-00ADD8?logo=go&logoColor=fff)](https://go.dev)
[![C++](https://img.shields.io/badge/C++-00599C?logo=cplusplus&logoColor=fff)](https://isocpp.org/)
[![Linux](https://img.shields.io/badge/Linux-000?logo=linux&logoColor=fff)](https://kernel.org/)
[![AWS](https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=fff)](https://aws.amazon.com/)

</div>

---

## Receipts (short)
- **Rust-AI** — CPU inference engine with arena allocators & SIMD. ~**3× faster** than Python baselines on targeted workloads.
- **void-go** — minimal web stack; low-alloc pipelines. ~**100k+ req/s** synthetic, stable P99s.
- **fasthttp / http2** — protocol work (stream scheduling, perf tuning) used in prod.

> Deterministic latency > peak throughput. I optimize for **P99/P999**, not the demo slide.

---

## Toolbox
`Rust` · `Go` · `C/C++` · `epoll/kqueue` · `io_uring` (selectively) · `SIMD` · `ring buffers` · `lock-free queues`  
`HTTP/1.1/2` · `gRPC` · `WebSockets` · `H2 flow-control` · `HPACK/QPACK`  
`PostgreSQL` · `Redis` · `MongoDB (used judiciously)`  
`perf/pprof` · `flamegraphs` · `bcc/eBPF` · `tracing` · `GitHub Actions` · `Docker/K8s`

---

## Approach
1. **Measure first** (profile, trace, budget).
2. **Fix the heaviest edge** (allocs → copies → locks → syscalls).
3. **Prove it** (A/B, SLO deltas, cost per 10k req).
4. **Make it boring** (observability, blast-radius, rollback).

---

## Selected Work
- [Rust-AI](https://github.com/ToughLad/Rust-AI) — memory-safe inference, cache-aware datastructures.
- [void-go](https://github.com/ToughLad/void-go) — zero-allocation hot path, sane defaults.
- [fasthttp/http2](https://github.com/dgrr/http2) — correctness & throughput under load.

<details>
  <summary><b>Benchmark notes</b></summary>

- Throughput figures are synthetic (wrk/vegeta) on commodity hardware; I prioritize tail-latency & jitter.  
- Real benefits came from: pooling, scatter/gather I/O, fewer copies, bounded queues, and backpressure.
</details>

---

## Now
- Tightening **tail latency** on Rust services (tracing-first).
- Protocol work (HTTP/2 scheduling, flow-control fairness).
- Teaching teams to go from “it’s fast here” → “it’s fast **in prod**”.

---

## Background (one line)
Saudi Aramco (industrial/RT), IVC Valves (control systems), NoMoreCopyright (high-volume platform), Upwork (top-rated systems work).

---

## Contact
**hello@toughlad.dev** · **https://toughlad.dev**  
Available for **performance audits**, **backend architecture**, and **protocol implementations**.

---

> “Make it work. Make it right. **Make it fast.**”  
<sub>Knowing when to optimize is the actual skill.</sub>
