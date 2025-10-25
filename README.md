# ToughLad — systems & performance

> I ship low-latency services, make code cheaper, and **own the tail**.

<div align="center">

[![Rust](https://img.shields.io/badge/Rust-000?logo=rust)](https://www.rust-lang.org/)
[![Go](https://img.shields.io/badge/Go-00ADD8?logo=go&logoColor=fff)](https://go.dev)
[![C++](https://img.shields.io/badge/C++-00599C?logo=cplusplus&logoColor=fff)](https://isocpp.org/)
[![Linux](https://img.shields.io/badge/Linux-000?logo=linux&logoColor=fff)](https://kernel.org/)
[![AWS](https://img.shields.io/badge/AWS-232F3E?logo=amazonaws&logoColor=fff)](https://aws.amazon.com/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?logo=linkedin&logoColor=fff)](https://www.linkedin.com/in/toughlad/)

</div>

---

## Recruiter snapshot
- Roles: systems / backend / performance (Rust, Go, C/C++)
- Strengths: protocol work, observability, P99/P999 control, cost/perf trade-offs
- Scale: millions+ requests; deterministic behavior in prod
- Availability: audits, architecture, staff-level IC

---

## Receipts
- **Rust-AI** — CPU inference with arena allocators + SIMD. ~**3× faster** than Python baselines on targeted workloads.
- **void-go** — minimal web stack with low-alloc hot path. ~**100k+ req/s** synthetic, stable P99s.
- **fasthttp/http2** — stream scheduling + perf tuning used in production ecosystems.

> Deterministic latency > headline throughput. I optimize for **tail** and **jitter**.

---

## Toolbox
`Rust` · `Go` · `C/C++` · `epoll/kqueue` · `io_uring` (selective) · `SIMD` · `ring buffers` · `lock-free`  
`HTTP/1.1/2` · `gRPC` · `WebSockets` · `flow control` · `HPACK/QPACK`  
`PostgreSQL` · `Redis` · `MongoDB (used judiciously)`  
`perf/pprof` · `flamegraphs` · `bcc/eBPF` · `tracing` · `GitHub Actions` · `Docker/K8s`

---

## Approach
1) Measure first (profiles, traces, budgets)  
2) Fix the heaviest edge (allocs → copies → locks → syscalls)  
3) Prove it (A/B, SLO deltas, cost per 10k req)  
4) Make it boring (observability, blast-radius, rollback)

---

## Selected projects
- [Rust-AI](https://github.com/ToughLad/Rust-AI) — memory-safe inference, cache-aware data structures  
- [void-go](https://github.com/ToughLad/void-go) — zero-allocation hot path, sane defaults  
- [fasthttp/http2](https://github.com/dgrr/http2) — correctness & throughput under load

<details>
  <summary><b>Benchmark notes</b></summary>
Throughput numbers are synthetic (wrk/vegeta) on commodity hardware; I prioritize tail-latency & jitter. Real wins came from pooling, scatter/gather I/O, fewer copies, bounded queues, and backpressure.
</details>

---

## Contact
**Email:** hello@toughlad.dev

---

> “Make it work. Make it right. **Make it fast.**”
