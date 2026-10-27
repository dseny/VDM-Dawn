# VDM-Dawn
A MoE-architecture model post-trained specifically for cybersecurity scenarios.

# Evaluation Overview
Our VDM-Dawn model was evaluated on a subset of **ExploitGym**, using commit `e4123d043774623b2274e6bbe0155a423d631f0a` of the benchmark repository.

| Configuration | Setting |
|---|---|
| Benchmark | ExploitGym |
| Benchmark revision | `e4123d043774623b2274e6bbe0155a423d631f0a` |
| Defense configuration | Mitigations disabled |
| Userspace | `exp.none` |
| V8 | `nodefense` |
| Kernel | `default` capability set |
| Agent | Claude Code driving VDM-Dawn |
| Evaluation criterion | On-target flag capture |

Across the **398** evaluated instances, the agent successfully obtained the corresponding `flag.txt` in **230** cases, while **168** instances ended without a captured flag. Whether a captured flag was **on target** was determined independently by a judge model, GPT-5.6-sol, running within Claude Code.


# Aggregate Performance of VDM-Dawn
A total of **398 instances** were evaluated. VDM-Dawn captured flags in **230** of them, corresponding to a flag-capture rate of **57.8%**. Among these 230 captures, **160 were classified as on-target**, while **70 were classified as off-target**.


> **230 / 398** — Instances with captured flags  
> **160 / 230** — On-target captures  
> **70 / 230** — Off-target captures

The resulting outcome distribution is:

| Outcome | Count |
|---|---:|
| On-target capture | **160** |
| Off-target capture | **70** |
| No captured flag | **168** |
| **Total** | **398** |


## Task Family
The evaluation set consists of three task families: Userspace, V8, and Kernel. Kernel and V8 show the highest flag-capture rates, while Userspace accounts for the majority of instances that ended without a captured flag.

| Task Family | Evaluated | Captured | On-target | Off-target |
|:--|--:|--:|--:|--:|
| Userspace | 298 | 164 | 95 | 69 |
| V8 | 54 | 33 | 32 | 1 |
| Kernel | 46 | 33 | 33 | 0 |
| **All** | **398** | **230** | **160** | **70** |

The family-level results therefore show that **164 of 298 Userspace**, **33 of 54 V8**, and **33 of 46 Kernel** instances produced a captured flag, yielding **230 captures from 398 evaluated instances** in total.
