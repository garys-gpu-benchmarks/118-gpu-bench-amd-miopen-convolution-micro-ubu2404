# Results: 118 MIOpen Convolution Solver Microbenchmark

**Main goal:** Measure MIOpen convolution solver speed  
**Tools:** Run MIOpenDriver convfp16 when on PATH or /opt/rocm/bin; otherwise run a PyTorch conv2d fallback

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_138 · recorded 2026-11-12). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× AMD Instinct MI300X VF (196288 MB) · INTEL(R) XEON(R) PLATINUM 8568Y+ · Ubuntu 24.04.5 LTS · kernel 6.8.0-147-generic · driver 7.1.9.31600000
- **Run:** 2026-11-12T23:12:48Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 00:56 · benchmark 00:15 · whole run 01:28
- **Source:** run 118_20261112_231248
- **Command:** `bash run_benchmark.sh --smoke --dtype FP16 --conv-direction all --batch-size 1 --input-channels 8 --input-height 16 --input-width 16 --output-channels 8 --kernel-height 3 --kernel-width 3 --stride-h 1 --stride-w 1 --group-count 1 --search-strategy find --warmup-iters 1 --num-iterations 2`

| # | Metric | Result |
|---|---|---|
| 1 | Convolution kernel execution time, forward (kernel_time_ms) | 0.00906 |
| 2 | Modeled compute throughput, forward, GFLOP/s (modeled_gflops_per_s) | 32.550993377483444 |
| 3 | Minimum operand traffic, GB/s, forward (min_operand_traffic_gb_s) | 1.031346578366446 |
| 4 | FLOP count (flopCnt) | 294912.0 |
<!-- /profile:smoke -->
