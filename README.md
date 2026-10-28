# Grafting and Fathoming

**From Agent Skills to Executable Environments: Frontier-Targeted Training for Tool-Use LLMs**

**EMNLP 2026 Main**

Dawei Zhang, Yubin Huangfu, Kyle Yusong Yao, Boyu Wei, Zongqi Han, Likang Wu, Hongke Zhao, Ming He, and Jianping Fan

[Paper](https://aclanthology.org/2026.emnlp-main.305/) · [PDF](https://aclanthology.org/2026.emnlp-main.305.pdf) · [Code](https://github.com/zhangdw156/grafting) · [Grove-500](https://huggingface.co/datasets/zhangdw/grove-500) · [Grove-5K](https://huggingface.co/datasets/zhangdw/grove-5k) · [Fathom-12K](https://huggingface.co/datasets/zhangdw/fathom-12k)

This repository is the paper and resource hub for Grafting and Fathoming. The implementation and usage instructions are maintained in [Grafting](https://github.com/zhangdw156/grafting).

## Overview

**Grafting** turns agent skills into self-contained executable environments, then generates and verifies multi-turn tool-use trajectories. **Fathoming** probes the target model, selects training examples near its current capability boundary, and applies iterative GRPO training.

![Overview of Grafting and Fathoming: skill-seeded environment synthesis, verified trajectory generation, and frontier-targeted training.](https://raw.githubusercontent.com/zhangdw156/grafting/main/assets/pipeline.png)

## Released Resources

**October 28, 2026:** Grafting, Grove-500, Grove-5K, and Fathom-12K are publicly available.

| Resource | Contents | License |
|---|---|---|
| [Grafting](https://github.com/zhangdw156/grafting) | Environment synthesis, task generation, simulation, verification, probing, data selection and export, plus training reward and BFCLv4 evaluation integrations | MIT |
| [Grove-500](https://huggingface.co/datasets/zhangdw/grove-500) | 500 executable environments used in the end-to-end experiments | Apache-2.0 |
| [Grove-5K](https://huggingface.co/datasets/zhangdw/grove-5k) | 5,101 executable environments from the scaled synthesis pipeline | Apache-2.0 |
| [Fathom-12K](https://huggingface.co/datasets/zhangdw/fathom-12k) | 12,745 verified multi-turn tool-use trajectories generated from Grove-500 | Apache-2.0 |

For installation, pipeline commands, probing, and the released training and evaluation integrations, see the [Grafting README](https://github.com/zhangdw156/grafting#readme). Each dataset page provides download instructions and its data format.

## Main Results

Two rounds of Fathoming starting from **Qwen3-4B-Instruct-2507** produce **Fathom-4B**. The paper reports the following accuracy scores (%):

| Benchmark | Qwen3-4B-Instruct-2507 | Fathom-4B | Gain |
|---|---:|---:|---:|
| BFCLv4 multi-turn | 22.0 | 39.7 | +17.7 points |
| ComplexFuncBench per-call | 49.6 | 61.6 | +12.0 points |

See the [paper](https://aclanthology.org/2026.emnlp-main.305/) for evaluation settings, ablations, and limitations.

## Citation

If you use this work, please cite the published EMNLP paper:

```bibtex
@inproceedings{zhang-etal-2026-agent-skills,
    title = "From Agent Skills to Executable Environments: Frontier-Targeted Training for Tool-Use {LLM}s",
    author = "Zhang, Dawei  and
      Huangfu, Yubin  and
      Yao, Kyle Yusong  and
      Wei, Boyu  and
      Han, Zongqi  and
      Wu, Likang  and
      Zhao, Hongke  and
      He, Ming  and
      Fan, Jianping",
    editor = "Lee, Hung-Yi  and
      Dev, Sunipa  and
      Li, Jessy  and
      Elliott, Desmond",
    booktitle = "Proceedings of the 2026 Conference on Empirical Methods in Natural Language Processing",
    month = oct,
    year = "2026",
    address = "Budapest, Hungary",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2026.emnlp-main.305/",
    pages = "7026--7050",
    ISBN = "979-8-89176-459-0"
}
```
