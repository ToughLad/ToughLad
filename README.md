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

## Recruiter snapshot
- Roles: systems / backend / performance (Rust, Go, C/C++)
- Strengths: protocol work, observability, P99/P999 latency control, cost/perf tradeoffs
- Scale: millions+ requests, safety-aware and prod-ready
- Availability: audits, architecture, and staff-level IC

---

## Receipts
- **Rust-AI** — CPU inference with arena allocators + SIMD. ~**3× faster** than Python baselines on targeted workloads.
- **void-go** — minimal web stack with low-alloc hot path. ~**100k+ req/s** synthetic, stable P99s.
- **fasthttp/http2** — stream scheduling + perf tuning in production ecosystems.

> Deterministic latency > headline throughput. I optimize for **tail** and **jitter**.

---

## Previous work (impact snapshots)

**Saudi Aramco — Software Engineer, Industrial Systems**  
_Stack:_ C/C++, RT Linux, telemetry, PLC/gateway integrations  
_Impact:_ Built real-time control modules with watchdogs and bounded queues; reduced jitter on critical I/O paths and improved recovery characteristics for safety-sensitive workloads.

**IVC Valves — Backend → Backend Software Engineer**  
_Stack:_ Go, TypeScript, PostgreSQL, Redis, MQTT  
_Impact:_ Delivered control + monitoring apps; added streaming ingestion with backpressure; cut queue stalls and elevated time-to-first-plot; CI/CD with reproducible releases.

**NoMoreCopyright — Full-Stack / Platform Architecture**  
_Stack:_ Node/Rust/Go, Redis, MongoDB, AWS, Cloudflare, feature flags, tracing  
_Impact:_ Scaled services to millions+ requests; introduced cache layers, query pruning, and key TTLs to reduce MongoDB ops and spend; added tracing, rate limits, and error budgets to make performance boring in prod.

**Upwork — Freelance Systems Programmer (2019–present)**  
_Stack:_ Rust, Go, C++, Linux, networking  
_Impact:_ 20+ deliveries (top-rated): performance audits, backend rewrites, observability rollouts, protocol implementations. Clear before/after metrics and docs included.

---

## Toolbox
`Rust` · `Go` · `C/C++` · `epoll/kqueue` · `io_uring` (selective) · `SIMD` · `ring buffers` · `lock-free`  
`HTTP/1.1/2` · `gRPC` · `WebSockets` · `flow control` · `HPACK/QPACK`  
`PostgreSQL` · `Redis` · `MongoDB (used judiciously)`  
`perf/pprof` · `flamegraphs` · `bcc/eBPF` · `tracing` · `GitHub Actions` · `Docker/K8s`

---

## Approach
1. Measure first (profiles, traces, budgets).  
2. Fix the heaviest edge (allocs → copies → locks → syscalls).  
3. Prove it (A/B, SLO deltas, cost per 10k req).  
4. Make it boring (observability, blast radius, rollback).

---

## Selected projects
- [Rust-AI](https://github.com/ToughLad/Rust-AI) — memory-safe inference, cache-aware data structures.
- [void-go](https://github.com/ToughLad/void-go) — zero-allocation hot path, sane defaults.
- [fasthttp/http2](https://github.com/dgrr/http2) — protocol correctness and throughput under load.

<details>
  <summary><b>Benchmark notes</b></summary>
Throughput numbers are synthetic (wrk/vegeta) on commodity hardware. Real gains came from pooling, scatter/gather I/O, fewer copies, bounded queues, and backpressure.
</details>

---

## Now
- Tightening tail latency on Rust services (tracing-first)  
- HTTP/2 scheduling + flow-control fairness  
- Coaching teams from “fast in dev” to “fast in prod”

---

## Contact
**hello@toughlad.dev** · **https://toughlad.dev**

---

> “Make it work. Make it right. **Make it fast.**”
