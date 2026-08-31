# The Turkey Problem

## Abstract
In agricultural logistics, batch management requires continuous adaptation to fluctuating constraints. This repository defines "The Turkey Problem": a dynamic mass-balance model where both the target capacity ($n_i$) and the uncaptured carryover ($m$) vary, forcing real-time adjustments in collection strategy.

## Context
While helping on a farm, I observed that collection targets are never static. In this setting, a group of turkeys gathered for the loading machine is called a **"gabbiotto"** (batch). Because operational conditions (space, terrain, fatigue) constantly shift, the target capacity for each batch changes dynamically, compounding the effect of escaped turkeys.

## The Problem
Let $n_i$ be the target capacity for the current batch $i$ (which fluctuates around 300–400). If $m$ turkeys escape from the previous operation and carry over, they directly occupy space in the current target. 

The system follows a dynamic mass-balance equation:

$$m + \text{new\_turkeys} = n_i$$

Therefore, the required new captures must adapt in real-time: $\text{new\_turkeys} = n_i - m$.

The core challenge lies in controlling this variance. Both $n_i$ (the shifting goal) and $m$ (the fluctuating residue) create a moving target. The system hits an *infringed state* when carryover $m$ crosses a critical threshold relative to the shifting target, requiring explicit recalculation rather than routine execution.

## The Mass-Balance Logic
- **Stable State ($m < m_{\min}$):** Minor residue. The shifting target $n_i$ is managed through standard execution; the delta is absorbed naturally.
- **Infringed State ($m \ge m_{\min}$):** Critical constraint. The combination of high carryover and a shifting target forces an active state update where the worker must explicitly recalculate the exact subset of new elements required to hit $n_i$.

## Methodology & Acknowledgments
- **Concept & Logic:** Derived from real-world agricultural logistics and dynamic mass-balance principles.
- **Simulation Code:** Structured and generated with the assistance of AI to build a functional Proof of Concept (PoC) handling variable targets and state carryover.
