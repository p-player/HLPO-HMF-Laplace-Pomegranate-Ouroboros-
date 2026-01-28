# HLPO: Physics-Informed Sparse Attention | 全息低渗透率优化**

![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)
![Status: Verified](https://img.shields.io/badge/Status-Verified-success)
![Platform: CUDA/RTL](https://img.shields.io/badge/Platform-CUDA%20%7C%20RTL-blue)

## ⚡️ The Core Premise / 核心论点

**"50% of connections in Large Language Models are thermal noise."**
**“大语言模型中 50% 的连接本质上只是热噪声。”**

HLPO is a full-stack architectural overhaul—from algorithm to silicon—designed to prove that **Dark Silicon** is the future of AI compute. By strictly enforcing a **hard mass gate** on attention matrices, we achieve:
HLPO 是一场从算法到硅片的全栈架构重构，旨在证明 **“暗硅 (Dark Silicon)”** 才是 AI 计算的未来。通过在注意力矩阵上实施严格的 **“硬质量门控 (Hard Mass Gate)”**，我们实现了：

- **0.08 Loss Gap** at 50% sparsity. (50% 稀疏度下 Loss 仅增 0.08)
- **5.26x Speedup** on Native Inference (M2 Ultra). (原生推理端到端 5.26 倍加速)
- **99% Silent Ratio** on custom RTL hardware. (RTL 硬件上 99% 的静默率)

---

## 📂 Repository Architecture / 仓库架构

This repository contains the complete technical evidence chain (Report 2), proving the feasibility of HLPO across the entire computing stack.
本仓库包含完整的技术证据链 (Report 2)，验证了 HLPO 在全计算栈上的可行性。

| Level | Component | Key Validation (核心验证) | Key Metric (核心指标) |
| :--- | :--- | :--- | :--- |
| **L1: Algorithm** | **A/B Test** & **7B Finetunes** | Verified on Mistral-7B (System Constraints) | **Loss 3.72 -> 2.35** (Finetuning) |
| **L2: Software** | **Triton Kernel** | Context > 4K Long-Sequence Benchmark | **2.56x Speedup** (vs FlashAttn) |
| **L3: Hardware** | **Native Inference** | Weight-based Gating on Python/MPS | **5.26x Speedup** (End-to-End) |
| **L4: Silicon** | **HPU RTL** | Dedicated Accelerator Power Analysis | **>99% Energy Saving** (Dark Silicon) |

---

## 🚀 Quick Navigation / 快速导航

### 1. The "Why" (Algorithm)
> *How can removing 50% of the brain keep 99.5% of the intelligence?*
> *为什么切除 50% 的大脑还能保留 99.5% 的智力？*
- **Evidence**: [HLPO_vs_Dense_Report](./Part1_ABTest/HLPO_vs_Dense_Report_CN.pdf) (100M A/B Test)
- **Insight**: Precision alignment reached **98.43%**, proving "Holographic Redundancy".
- **Insight**: 稀疏化后的特征向量与全量计算保持了 **98.43%** 的余弦相似度。

### 2. The "How" (Software)
> *How to beat $O(N^2)$ complexity with Python?*
> *如何用 Python 逻辑击败 $O(N^2)$ 的物理复杂度？*
- **Evidence**: [Triton Benchmark](./Part2_Triton/Showcase_Report.pdf) (Kernel Optimization)
- **Evidence**: [Native Inference Report](../HLPO%20Report/README.md) (See previous report for M2 Ultra data)

### 3. The "What" (Silicon)
> *What does a truly sparse chip look like?*
> *一颗真正的“稀疏芯片”长什么样？*
- **Evidence**: [HPU Power Report](./Part4_RTL/HPU_Power_Report.pdf) (Waveform Analysis)
- **Fact**: 99.6% of the time, the chip is "Dark" (Idle), consuming near-zero power.

---

## 🛠 Tech Stack / 技术栈
- **Algorithm**: PyTorch, Dynamic Sparse Attention
- **Kernel**: OpenAI Triton, NVIDIA CUDA (Tensor Cores/WMMA)
- **Hardware**: Verilog HDL, Icarus Verilog
- **Analysis**: Python (Matplotlib, Pandas)

---

## 🛡 Security & Compliance / 安全与合规
All assets in this repository have passed strict security audits:
本仓库内所有资产均已通过严格的安全审计：

1.  **Sanitized**: Proprietary formulas and coefficients have been removed. (核心公式与系数已脱敏)
2.  **Safe**: No raw VCD dumps or model weights are included. (不含原始波形或模型权重)
3.  **Real**: All performance data flows from real-world experiments. (所有数据源自真实实验)

> **Note**: This is a technical showcase bundle. For full source code access, please contact the architecture team.
> **注**: 本项目为技术展示包。如需完整源代码，请联系架构团队。

---

**© 2026 HLPO Architecture Team.**
This work is licensed under a [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License](http://creativecommons.org/licenses/by-nc-nd/4.0/).
*本作品采用知识共享署名-非商业性使用-禁止演绎 4.0 国际许可协议进行许可。*
