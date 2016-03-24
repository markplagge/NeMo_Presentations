## Neuromorphic Hardware
### Specialized Processing

- Uses Artificial Neural Network concepts
- Excellent for finding patters in data
- Great data analysis capability
Note:
I'm not going to go into too much detail here as Noah discussed this in more detail last meeting.
Neuromorphic hardware allows for specialized data classification and analysis.


## Neuromorphic Hardware
### Low Power

- IBM TrueNorth processor uses 65 mW
	*(That's Milliwatts!)*

Note:
The interesting thing about this hardware, to our research group, is the
power usage. This is a tiny amount of power usage.
As designs improve - perhaps we will have neuromorphic hardware in smartphones!


## Neuromorphic Hardware
### New Algorithms
Neuromorphic computing is "Non von Neumann"
- Does not operate using traditional algorithms
- New programming paradigms needed for adoption

Note:
Programming the hardware is tricky.
We probably won't be seeing a GCC compiler for TrueNorth for a while
IBM has provided a couple of programming tools:
TEA and corelets.


## Demand and Potential
#### Exascale Computing
-	Transitioning to “Fat Nodes”
-	Titan
	- Released in 2013 has 18,688 CPUs and 18,688 GPUs        
  - Uses 8.2 MW of Power
	- 10 petaflops
- Tianhe-2 has 32,000 CPUs with accelerators
	- 33.86 petaflops
	- Uses 24 MW of Power!
#### NASA vision report suggests in 2030:
-   New systems with have only 20,000 compute nodes
Note:
As new supercomputer demands are met, the power requirements have gone up.
The NASA report suggests that by 2030 new supercomputers will only have about 20,000 compute nodes
How will we achieve exascale performance with fewer nodes?


### Exascale Computing
-   Accelerator cards are becoming increasingly important
-   GPU, Intel PHI
-   Why not neuromorphic hardware?  <!-- .element: class="fragment roll-in visible current-fragment" data-fragment-index="1" -->
       - Low Power  <!-- .element: class="fragment roll-in visible current-fragment" data-fragment-index="1" -->
       - Excellent Machine Learning  <!-- .element: class="fragment roll-in visible current-fragment" data-fragment-index="1" -->
Note:
Supercomputers will have to make use of more dedicated acceleration technology
So - why not neuromorphic hardware as well?


## Designing the Next Generation Supercomputers


### Simulation of New Technologies
-   Allows testing of hardware configurations
-   Enables rapid prototyping of systems

### CODES
-		Based on ROSS
-		Enables simulation of new supercomputer designs


### Neuromorphic Hardware Simulation
-   Should Allow for Chip Simulation
#### Needs to simulate
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
-	Third generation neuron simulation
- Developed to simulate biological functions - not for machine learning
- Neuromorphic computing has been shown to be viable for computing

### Comparison with MLP
- Include concept of time
- Neurons do not need to fire at every timestep, $t$
- Activation level is increased with spikes

## Introductions
-	First scientific model developed in 1952 by Hodgkin and Huxley


### Current Hardware
- Current hardware uses "spiking neurons"
	- Neurons output a 1 or 0
	- Integration is generally simple (no sigmoid functions yet)
	- Significant research is underway


### Leaky integrate-and-fire:
$$V\_j(t) =  V\_j(t-1) \sum_{i=0}^{n-1} \left[ x_i(t) \, s_i \right]$$

- Takes the sum of all of the input synapses.
	- $x$ is the on/off state of the synapse
	- $s_i$ is the synapse weight
	- $V_j(t)$ is the neuron voltage at time $t$


### Leaky integrate-and-fire
*Leak and reset for neuron $j$:*

- Leak: <!-- .element: class="fragment roll-in visible current-fragment" data-fragment-index="1" -->
$$V_j(t) = V_j(t) - \lambda_j $$
- Spike & Reset: <!-- .element: class="fragment roll-in visible current-fragment" data-fragment-index="3" -->
\begin{align}&\textbf{if}~~V\_j(t) \geq \alpha\_j: \notag \\\\&\qquad \text{Spike}\notag \\\\ &\qquad V\_j(t)= R\_j \notag \\\\ &\textbf{end if} \notag \end{align}

- $\lambda_j$ is the leak value of the neuron.  <!-- .element: class="fragment roll-in visible current-fragment" data-fragment-index="1" -->
- $\alpha_j$ is the threshold of the neuron. <!-- .element: class="fragment roll-in visible current-fragment" data-fragment-index="3" -->
- $R_j$ is the reset voltage. <!-- .element: class="fragment roll-in visible current-fragment" data-fragment-index="3" -->


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
