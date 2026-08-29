# The Turkey Problem 

## Abstract
In dynamic agricultural logistics, loading turkeys onto a conveyor belt presents a critical decision-making problem. This repository defines "The Turkey Problem": calculating the absolute threshold of escaped turkeys before a worker's spatial and visual estimation for the next batch is compromised.

## Context
While I was helping a friend load turkeys on a farm, I conceptualized this problem. In this setting, the specific group of turkeys gathered by the worker to be loaded onto the machine is called a **"gabbiotto"** (batch).

## The Problem
When collecting a batch of $n$ turkeys (where $n$ is typically 300-400), a certain number of animals will inevitably escape and mix back into the remaining flock. The core problem lies in the spatial estimation for the *subsequent* batch. 
If too many turkeys escape, the worker's visual and spatial references are skewed. Instead of gathering the intended 400 turkeys for the next batch, this compromised perception might lead the worker to accidentally enclose a much larger group (e.g., 450), entirely disrupting the operational flow and decision-making process.

## The Solution: Error-Rejection Theory
Through empirical observation and the application of statistical error-rejection (identifying outliers versus normal deviation), the critical threshold for the decision-making compromise is defined by absolute numbers.

- **Stable State (4-5 escapes):** On average, 4 to 5 turkeys escape per batch. This is physiological background noise. The worker's visual references remain intact, and they can accurately collect 400 turkeys for the next batch without cognitive recalibration.
- **Compromised State (12-15 escapes):** If the number of escaped turkeys reaches the **12-15** range, the error becomes an anomaly (an outlier). A group of 12-15 turkeys is physically large enough to pollute the remaining flock's density and skew the worker's spatial perception. Without active recalibration, the worker will unknowingly collect an oversized next batch.

*Note: This is a hypothesized solution based on field observation. It might not be the definitive one, and I welcome contributions, corrections, or alternative mathematical models from the community.*

## Scientific Parallels
This rural intuition perfectly mirrors:
1. **Cognitive Ergonomics:** Managing cognitive load and visual heuristics in repetitive physical tasks.
2. **Deadbands in Control Systems:** Preventing oscillation and over-correction in automated systems.
3. **Statistical Process Control:** Shewhart's distinction between common cause variation (noise, 4-5 escapes) and special cause variation (anomalies, 12-15 escapes).
