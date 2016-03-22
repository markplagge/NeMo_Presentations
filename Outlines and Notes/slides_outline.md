# NeMo
#### A Parallel Discrete Event Neuromorphic Hardware Simulation Model



## Overview
- Neuromorphic Hardware
- Neuromorphic Algorithms
- Demand & Potential
- Contributions of NeMo
- Features of NeMo
- Model Validation
- Experimental Results
- Comparison with IBM COMPASS
- Future Work



## Neuromorphic Hardware
### Specialized Processing

- Uses Artificial Neural Network concepts
- Excellent for finding patters in data
- Great data analysis capability


## Neuromorphic Hardware
### Low Power

- IBM TrueNorth processor uses 65 mW
	*(That's Milliwatts!)*


## Neuromorphic Hardware
### New Algorithms
Neuromorphic computing is "Non von Neumann"
- Does not operate using traditional algorithms
- New programming paradigms needed for adoption


## Demand and Potential
#### Exascale Computing
-	Transitioning to “Fat Nodes”
-	Titan – Revealed in 2013 has 18,688 CPUs and 18,688 GPUS        
    Uses 8.2 MW of Power! 
-   Tianhe-2 has 32,000 CPUs with accelerators
    
    Uses 24 MW of Power!  
#### Nasa vision report suggests in 2030:
-   New systems with have only 20,000 compute nodes


### Exascale Computing
-   Accelerator cards are becoming increasingly important
-   GPU, Intel PHI
-   Why Not Neuromorphic hardware?
        Low Power
        Excellent Machine Learning



## Designing the Next Generation Supercomputers


### Simulation of New Technologies
-   Allows testing of hardware configurations
-   Enables rapid prototyping of systems


### Neuromorphic Hardware Simulation
-   Should Allow for Chip Simulation with:
	-   Current hardware design
	-   Future and theoretical hardware



# Contributions
### NeMo – An Open Source Neuromorphic Hardware Simulation Model


## NeMo
#### Design and implementation
-   Implemented using ROSS
-   Event-Driven
-   Massively Parallel
-   Optimistic Event Scheduling
-   Supports Reverse Computation


### NeMo
-	Open Source
-	Flexible Hardware Models
-   Supports current neuromorphic design
-   Can simulate novel designs
-   Can even simulate currently "impossible" designs


### NeMo
#### Large Scale Simulation Support
-   Currently tested to simulate 65,536 neurosynaptic cores
-   Further scale-ups very feasible


### NeMo
#### Potential for new spiking neuron models
-   Will support other Spiking Neural Network models in the future
-   Validated using IBM’s TrueNorth Model



# Neuromorphic Computing Models
## A brief overview


### Basics
-	Based on Artificial Neural Network (ANN) concept
- 	Developed to simulate biological functions - not for machine learning
-	Recently, neuromorphic computing has been shown to be viable for computing


### Current Hardware
- Current hardware uses "spiking neurons"
	- Neurons output a 1 or 0 
	- Integration is generally simple (no sigmoid functions yet)


### Leaky integrate-and-fire: 
$$V\_j(t) =  V\_j(t-1) \sum_{i=0}^{n-1} \left[ x_i(t) \, s_i \right]$$

- Takes the sum of all of the input synapses. 
	- $x$ is the on/off state of the synapse
	- $s_i$ is the synapse weight
	- $V_j(t)$ is the neuron voltage at time $t$


### Leaky integrate-and-fire
*Leak and reset for neuron $j$:*

- Leak: <!-- .element: class="fragment" data-fragment-index="1" -->
$$V_j(t) = V_j(t) - \lambda_j $$
- Spike & Reset: <!-- .element: class="fragment" data-fragment-index="3" -->
\begin{align}&\textbf{if}~~V\_j(t) \geq \alpha\_j: \notag \\\\&\qquad \text{Spike}\notag \\\\ &\qquad V\_j(t)= R\_j \notag \\\\ &\textbf{end if} \notag \end{align}

- $\lambda_j$ is the leak value of the neuron.  <!-- .element: class="fragment" data-fragment-index="1" -->
- $\alpha_j$ is the threshold of the neuron. <!-- .element: class="fragment" data-fragment-index="3" -->
- $R_j$ is the reset voltage. <!-- .element: class="fragment" data-fragment-index="3" -->


### Leaky integrate-and-fire
The previous formulas combine to form the basic LIF form:

**Integration:**
$$V\_j(t) =  V\_j(t-1) \sum_{i=0}^{n-1} \\left[ x\_i(t) \, s\_i \\right]$$

**Leak:**
\begin{equation}
        V_j(t) = V_j(t) - \lambda_j   \notag
\end{equation}

**Threshold check & Fire:**
\begin{align}&\textbf{if}~~V\_j(t) \geq \alpha\_j: \notag \\\\&\qquad \text{Spike}\notag \\\\ &\qquad V\_j(t)= R\_j \notag \\\\ &\textbf{end if} \notag \end{align}
