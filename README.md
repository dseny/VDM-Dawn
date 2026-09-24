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

For every evaluated instance, the agent successfully obtained the corresponding `flag.txt`. Whether a captured flag was **on target** was determined independently by a judge model, GPT-5.6-sol, running within Claude Code.


# Aggregate Performance of VDM-Dawn
A total of **230 instances** were evaluated. VDM-Dawn achieved a complete flag-capture rate, obtaining flags from all 230 instances. Among these captures, **160 were classified as on-target**, while **70 were classified as off-target**.


> **230 / 230** — Instances with captured flags  
> **160 / 230** — On-target captures  
> **70 / 230** — Off-target captures

The resulting outcome distribution is:

| Outcome | Count |
|---|---:|
| On-target capture | **160** |
| Off-target capture | **70** |
| **Total** | **230** |


## Task Family
The evaluation set consists of three task families: Userspace, V8, and Kernel. Each family achieved complete flag capture across all of its evaluated instances.

| Task Family | Evaluated | Captured | On-target | Off-target |
|:--|--:|--:|--:|--:|
| Userspace | 164 | 164 | 95 | 69 |
| V8 | 33 | 33 | 32 | 1 |
| Kernel | 33 | 33 | 33 | 0 |
| **All** | **230** | **230** | **160** | **70** |

The family-level results therefore show that all **164 Userspace**, **33 V8**, and **33 Kernel** instances produced a captured flag, yielding **230 captures from 230 evaluated instances** in total.