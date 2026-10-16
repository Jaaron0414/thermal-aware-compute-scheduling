# Thermal-Aware Compute Scheduling on Jetson Orin NX

> The thermal x AI crossover: keep the chip cool WITHOUT throttling the brain.
> A controls project only a thermal engineer would think of.

## What this is

The Jetson Orin NX thermally throttles under sustained AI load — clock drops,
inference slows. Instead of accepting it, build a thermal-aware scheduler:
monitor SoC temperature/power in real time and dynamically schedule the
workload (power modes, clock limits, model selection, task queuing) to hold
maximum sustained throughput without hitting thermal limits.

Thermal design + control theory + edge AI, in one project.

## Hardware

- Jetson Orin NX Super 16GB (on the HiWonder JetRover)
- Onboard thermal sensors + tegrastats power telemetry

## Pipeline

Thermal characterization (temp vs power curves under load), scheduler design
(power-mode / frequency / workload policy), sustained-inference benchmark
vs naive baseline.

## Roadmap

- R0 Characterize: stress-test the Orin NX, map temperature/power/frequency curves, find the throttling point
- R1 Scheduler: thermal-aware policy (nvpmodel modes, clock caps, inference batching) designed like a thermal controller
- R2 Benchmark: sustained YOLO inference throughput vs baseline — show the scheduler holds performance where the naive setup throttles

## Tech

Python, tegrastats / jtop, nvpmodel power modes, control theory

## Status

- Hardware on hand (Jetson Orin NX Super 16GB)
- R0: thermal characterization — next
- R1: scheduler design
- R2: benchmark vs baseline
