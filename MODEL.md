# 1. Purpose of the Model

MineTwin provides an offline engineering model to estimate which thermal operating point yields the best profitability for a Bitcoin mining setup under practical physical constraints.

The model is intended to support technical decision-making, not automated control. It translates engineering inputs into comparable operating-point outcomes so contributors can reason about tradeoffs between cooling effort, electrical use, hardware performance, and economic return.

# 2. System Boundaries

The modeled system is a mining installation segment composed of:
- Mining hardware as a heat-generating and performance-producing asset.
- Local thermal management conditions that influence hardware operating temperature.
- Electrical consumption linked to operating condition.
- Economic context needed to convert technical outcomes into profitability indicators.

Boundary conditions:
- Time scale is operational (hours to days), not millisecond control behavior.
- The environment is represented by supplied operating conditions, not full building or climate simulation.
- Inputs are scenario-based and fixed for a simulation run.
- Outputs are comparative estimates across candidate operating points.

# 3. Modeling Scope (In Scope)

The MVP includes:
- Representation of energy use at candidate operating points.
- Representation of thermal state at a level sufficient to classify operating feasibility.
- Representation of mining performance impact from operating temperature/state.
- Representation of economic outcomes from energy cost, mining output estimate, and selected financial inputs.
- Constraint handling for physically or operationally infeasible points.
- Batch-style simulation for scenario comparison and operating-point selection.

The MVP prioritizes traceable assumptions and interpretable outputs over model breadth.

# 4. Explicit Non-Goals (Out of Scope)

The MVP does not include:
- Real-time control loops, actuator control, or direct hardware command.
- Full computational fluid dynamics, detailed rack-level airflow, or geometry-resolved thermal modeling.
- Degradation physics at component-material level.
- Firmware-level ASIC behavior emulation.
- Forecasting of market variables as a primary objective.
- Site-wide electrical network dynamics beyond simplified power availability limits.
- UI/dashboard features.

# 5. Key Physical Assumptions

Assumptions used to keep the MVP coherent and implementable:
- Operating points are evaluated as quasi-steady conditions rather than full transients.
- Hardware can be represented by aggregate thermal and electrical behavior parameters.
- Thermal condition materially affects effective mining performance and/or reliability envelope.
- Cooling effectiveness can be represented by simplified operating parameters rather than full spatial field simulation.
- Input measurements and vendor data are treated as conditionally reliable within stated ranges.
- External disturbances are represented through scenario parameters, not stochastic real-time streams.

Economic assumptions tied to physical outputs:
- Profitability is evaluated from scenario inputs and simulated operating condition, not from guaranteed future outcomes.
- Cost and revenue inputs are treated as user-provided scenario values for comparison, not truth claims about markets.

# 6. Level of Model Fidelity

The MVP targets engineering screening fidelity:
- High enough to reject clearly infeasible or economically dominated operating regions.
- High enough to reveal first-order tradeoffs between thermal margin, energy use, and expected output.
- Not high enough to substitute for detailed thermal design studies, compliance validation, or hardware certification testing.

Fidelity is intentionally limited to support fast iteration, explainability, and calibration against available operational data.

# 7. Intended Use of the Model

The model is intended for:
- Comparing candidate operating policies before deployment changes.
- Stress-testing assumptions under different environmental and economic scenarios.
- Supporting engineering discussions with explicit, auditable assumptions.
- Guiding where deeper instrumentation or higher-fidelity studies are worth the effort.

The model is not intended to be used as a sole authority for production risk acceptance.

# 8. Known Limitations

Current limitations include:
- Reduced thermal detail may hide local hotspots or short-lived events.
- Simplified performance response may underrepresent edge-case hardware behavior.
- Profitability outputs are sensitive to input quality and scenario framing.
- Constraint models may be incomplete where site-specific operating rules are unknown.
- Calibration quality depends on available measurement coverage and data hygiene.

As a result, outputs should be interpreted as decision support signals, not ground truth.

# 9. Future Extensions (Non-Commitment)

The items below are listed to clarify what is intentionally deferred, not to imply planned delivery.

Potential future extensions, without commitment to scope or timeline:
- Improved transient thermal behavior representation.
- More explicit reliability and derating treatment.
- Finer-grained coupling between cooling subsystem states and mining performance.
- Site-specific calibration workflows with uncertainty tracking.
- Structured scenario libraries for repeatable benchmarking.
- Interfaces for later CLI/REPL operation once core model behavior stabilizes.

Any extension should preserve explicit assumptions, testability, and clear model boundaries.
