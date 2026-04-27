# MineTwin

**Physics-based decision engine for Bitcoin mining operations.**

MineTwin helps mining operators determine **how to run their infrastructure** under real-world constraints — not just what happens.

---

## Why MineTwin exists

Bitcoin mining is not just a hashrate problem.

It is a **physical system**:

> electricity → heat → temperature → performance → revenue

Most tools focus on monitoring or control.
MineTwin focuses on something else:

> **finding the operating point that maximizes profitability given physical constraints.**

---

## What MineTwin does

MineTwin simulates mining behavior under different operating conditions and provides **actionable recommendations**.

### Inputs

* Electrical power availability (kW)
* Ambient temperature
* Cooling effectiveness
* Electricity cost
* Market assumptions (BTC price, etc.)

### Outputs

* Optimal operating point
* Estimated profitability
* Thermal feasibility
* Performance degradation
* Trade-offs between power, cooling, and efficiency

---

## Key Feature (WIP)

> MineTwin does not just simulate — it recommends.

Example output:

Optimal operating point:

* Power: 180 kW
* Cooling: 6.5
* Estimated hashrate: 92%
* Profit: +$124/day

Recommendation:
→ Increase cooling slightly instead of reducing power
→ Avoid high-power / low-cooling regimes (thermally inefficient)

---

## Model Philosophy

MineTwin is designed as an **engineering-grade decision support tool**:

* Physics-based (no black-box ML)
* Scenario-driven (not real-time control)
* Explicit assumptions
* Fast to iterate and calibrate

The goal is not perfect prediction, but **useful decisions**.

---

## Model Documentation

The full modeling assumptions, scope, and limitations are described in:

→ `MODEL.md`

---

## Current Status

This is an early-stage MVP focused on:

* validating the modeling approach
* identifying meaningful operating trade-offs
* building a usable decision engine

---

## Roadmap (informal)

* CLI for scenario execution
* Web interface for interactive exploration
* Scenario comparison
* Calibration with real-world data

---

## Disclaimer

MineTwin is a decision-support tool.

It provides **engineering estimates**, not guarantees.
Results depend on input quality and assumptions.

---

## License

Apache 2.0

## What this is not (yet)
- Not a commercial product
- Not open-source (for now)

🚧 More soon.
📩 minetwin@proton.me