Multi-Region Energy Consumption & Predictive Analysis Framework
Academic Project | MSc in Data Analytics | CCT College Dublin

Academic Research Focus
This project investigates the complex drivers of electricity consumption across multiple European regions. The core objective was to perform high-fidelity Applied Statistics and Sensitivity Analysis on massive datasets to identify the impact of celestial cycles and meteorological variance on energy demand.

The Engineering Challenge: "Stage 1" vs. Production
During initial development, the computational density of the statistical models (Monte Carlo simulations and High-Resolution Sensitivity Analysis) led to kernel collapse and memory overflow on standard CPU-based environments.
To overcome this, the project was re-architected to move from local compute to hardware acceleration:
VM & WSL Architecture: Engineered a specialized Ubuntu-based Virtual Machine and WSL2 environment to bypass local Windows OS resource limitations.
CUDA & GPU Acceleration: Implemented RAPIDS cuDF and cudf.pandas to leverage NVIDIA CUDA cores. This allowed for vectorized operations that were previously impossible, specifically for the high-frequency sampling required in sensitivity modeling.
Resource Orchestration: Developed environment-agnostic code (env_DiegoM.yml) to manage dependency conflicts and ensure optimal GPU memory allocation.

Deep Applied Statistics
Sensitivity Analysis (Sobol/S1): Calculated the first-order sensitivity of various features (Temperature, Solar Position, Wind Speed) to quantify their influence on regional energy prices and consumption.
Monte Carlo Simulations: Utilized stochastic modeling to forecast potential market outcomes, requiring the processing of tens of thousands of iterations—accelerated via GPU.
