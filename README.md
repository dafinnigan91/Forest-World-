# Forest World - Gaia Hypothesis Extension

An ecological simulation extending Lovelock's famous DaisyWorld model to incorporate real-world forest ecosystems and their environmental interactions. This project explores how multiple forest types (tropical, coniferous, deciduous) interact with climate forcing to investigate planetary temperature regulation through biological feedback mechanisms.

## Overview

### Background
The **Gaia Hypothesis**, proposed by James Lovelock, suggests that Earth's biosphere acts as a self-regulating system maintaining conditions suitable for life. The original **DaisyWorld model** (Lovelock & Watson, 1983) demonstrated how simple biological feedback could stabilize planetary temperature using two daisy species with different albedos.

### Forest World Extension
This project extends DaisyWorld by replacing hypothetical daisies with **real-world forest ecosystems** using empirical albedo data, temperature ranges, and growth parameters. The model investigates whether Earth's actual forest types can produce similar homeostatic temperature regulation.

## Features

### **Synthetic Ecosystem Modeling**
- **Three forest types**: Tropical, coniferous, and deciduous forests
- **Real albedo values**: Data from University Catholique de Louvain and Amazon studies
- **Temperature-dependent growth**: Species-specific optimal growth ranges and viability zones
- **Dynamic area allocation**: Grasslands respond to forest coverage changes

### **Scientific Methodology**
- **Hypothesis testing**: Statistical analysis of ecosystem performance differences
- **Stefan-Boltzmann physics**: Accurate temperature calculations using thermodynamic laws
- **Differential equations**: Replicator equations modeling population dynamics
- **Convergence analysis**: Iterative simulation until equilibrium conditions

### **Analysis**
- **Temperature regulation**: Tracks global warming vs. ecosystem feedback cooling
- **Ecosystem succession**: Multiple growth phases including expansion, decline, and stabilization
- **Statistical validation**: T-tests comparing ecosystem performance against null hypotheses
- **Future enhancements**: Proposed genetic algorithm for ecosystem evolution

## Implementation

### System Equations

**Planetary Albedo:**
```
A = αtr·atr + αco·aco + αde·ade + αgr·agr + αsa·asa + αsn·asn
```

**Population Growth (Replicator Equations):**
```
∂αtr/∂t = αtr[αgr·β(Ttr) - γ]
∂αco/∂t = αco[αgr·β(Tco) - γ]  
∂αde/∂t = αde[αgr·β(Tde) - γ]
```

**Temperature Calculation:**
```
T = (SL(1-A)/σ)^0.25
```

Where:
- `α` = albedo, `a` = area coverage
- `β(T)` = temperature-dependent birth rate
- `γ` = death rate, `SL` = solar luminosity
- `σ` = Stefan-Boltzmann constant

### Ecosystem Parameters

| Ecosystem | Albedo | Optimal Temp | Growth Range | Starting Area |
|-----------|---------|--------------|---------------|---------------|
| Tropical Forest | 0.13 | 23.5°C | 5°C - 45°C | 1% |
| Coniferous Forest | 0.15 | 21.5°C | 0°C - 35°C | 1% |
| Deciduous Forest | 0.20 | 22.5°C | 3°C - 40°C | 1% |
| Grasslands | 0.26 | N/A | N/A | 77% |
| Ice/Snow | 0.80 | N/A | N/A | 10% |
| Sand Desert | 0.45 | N/A | N/A | 10% |

## Installation & Usage

### Prerequisites
- Python 3.6+
- NumPy
- Matplotlib

### Running the Simulation
```bash
git clone https://github.com/yourusername/forest-world-gaia.git
cd forest-world-gaia
python forest_world_source_code.py
```

### Output
- **Figure 1**: Ecosystem coverage (%) vs solar luminosity
- **Figure 2**: Global temperature (°C) vs solar luminosity
- **Console output**: Convergence data and temperature regulation events

## Results

### Key Findings

**🌱 Ecosystem Dynamics:**
- **Deciduous forests**: Rapid early expansion (50% coverage), then sharp decline
- **Coniferous forests**: Peak at 39% coverage, gradual decline to extinction
- **Tropical forests**: Limited growth (8% max), early extinction due to high temperature requirements
- **Grasslands**: Dominant throughout, recovering from 30% to 77% final coverage

**🌡️ Temperature Regulation:**
- **Overall warming trend**: Consistent global temperature increase with solar flux
- **Brief cooling periods**: Two minor cooling events during ecosystem transitions
- **Limited homeostasis**: Unlike DaisyWorld, no sustained temperature stabilization achieved

**📈 Statistical Analysis:**
- **Tropical forests significantly underperformed** (p = 0.044) compared to other ecosystems
- **Grasslands approached significance** (p = 0.0502) for overperformance
- **Null hypothesis rejected**: At least one ecosystem differed significantly from others

### Implications
The model demonstrates that **real-world ecosystem complexity** does not automatically produce the elegant homeostatic regulation seen in simplified DaisyWorld. Multiple competing factors prevent sustained temperature stabilization.

## Technical Implementation

### Architecture
```
Forest World Simulation
├── Physical Constants (Stefan-Boltzmann, solar parameters)
├── Ecosystem Definitions (albedos, temperature ranges)
├── Differential Equation Solver (replicator equations)
├── Convergence Engine (iterative equilibrium finding)
└── Analysis Framework (statistical testing, visualization)
```

### Core Components

**1. Temperature Physics**
- Stefan-Boltzmann law implementation
- Local vs. global temperature calculations
- Heat transfer coefficients

**2. Population Dynamics**
- Birth rate functions based on temperature curves
- Death rate constants across ecosystems
- Area allocation constraints

**3. Numerical Methods**
- Convergence criteria for equilibrium detection
- Iterative solution of coupled differential equations
- Stability analysis for multiple attractors

## Scientific Significance

### Climate Modeling Applications
- **Ecosystem feedback loops** in climate systems
- **Albedo effects** of land-use change
- **Forest succession** under warming scenarios

### Gaia Theory Validation
- **Testing biological regulation** with real parameters
- **Homeostasis emergence** from ecosystem interactions
- **Teleology vs. mechanism** in planetary systems

### Future Extensions Proposed

**1. Genetic Algorithm Evolution**
```
Pseudocode:
1. Initialize 10-20 species per ecosystem with varying traits
2. Binary encode albedo/temperature/growth parameters
3. Select for temperature regulation fitness
4. Mutate and splice successful combinations
5. Evolve ecosystem adaptation over solar flux changes
```

**2. Dynamic Ice/Desert Coverage**
- Ice coverage responding to global temperature
- Desert expansion/contraction based on forest retreat
- Seasonal variations and hysteresis effects

## Academic Context

### Research Quality
- **Peer-reviewed methodology** following ecological modeling standards
- **Proper citations** of original DaisyWorld literature
- **Statistical rigor** with hypothesis testing and significance levels
- **Discussion of limitations** and methodological concerns

### Educational Value
- **Complex systems thinking** applied to climate science
- **Mathematical modeling** of ecological processes
- **Scientific programming** for hypothesis testing
- **Interdisciplinary approach** combining physics, ecology, and computation

## Development Notes

### Model Limitations
- **Grassland assumption**: Area fills automatically when forests decline (unrealistic)
- **Static ice/desert**: Fixed coverage doesn't respond to temperature changes
- **No spatial dynamics**: Zero-dimensional model ignores geographical factors
- **Simplified interactions**: No competition, migration, or genetic adaptation

### Code Quality
- **Modular design** based on Bennett et al. (2017) DaisyWorld implementation
- **Physical accuracy** using correct thermodynamic calculations
- **Parameterizable**: Easy to adjust ecosystem properties and test scenarios
- **Reproducible**: Fixed random seeds and documented parameters

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## References

- Lovelock, J.E. & Watson, A.J. (1983). The regulation of carbon dioxide and climate: Gaia or geochemistry. *Planet. Space Sci.* 31, 795-802
- Bennett, A., Greve, P. & Jaeger, E. (2017). DaisyWorld.py implementation
- University Catholique de Louvain (2008). Land surface albedo data
- Culf, A.D. et al. (1995). The albedo of Amazonian Forest and Ranch Land

## Acknowledgments

- **James Lovelock** for the foundational Gaia hypothesis and DaisyWorld model
- **Bennett et al.** for the open-source Python implementation framework

