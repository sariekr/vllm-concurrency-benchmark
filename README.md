# vLLM GPU Concurrency Benchmark

AIMultiple benchmark of GPT-OSS-20B inference on NVIDIA H100, H200, B200 and AMD MI300X. The study measures how simultaneous requests affect total output throughput and response latency.

> [Read the benchmark on AIMultiple](https://aimultiple.com/gpu-benchmark)

## Workload

Each GPU serves the same model through vLLM. Requests contain 1,000 input and 1,000 output tokens, with concurrency increasing from 1 to 512. Each level includes a warm-up period and a 180-second measurement window.

## Benchmark results

System output throughput at 512 concurrent requests:

| GPU | Output tokens/s |
| --- | ---: |
| B200 | 12,316 |
| H100 | 11,559 |
| H200 | 9,514 |
| MI300X | 6,922 |

B200 records the highest throughput at this load. Response latency also increases as concurrency rises, so the throughput figures need to be read alongside the latency curves in the article.

Results apply to the tested model and serving configurations. NVIDIA and AMD use different software builds and platform-specific settings.

## Ownership

The benchmark implementation was developed for AIMultiple and belongs to AIMultiple. This repository contains a documentation summary. Source code and benchmark datasets are not distributed here.
