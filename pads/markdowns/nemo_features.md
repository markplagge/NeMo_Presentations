

### NeMo Features
- "Heartbeat" messages that provide implicit synchronization
- Message fanout reduction through message routing
- Reverse computation for optimistic scheduling
- Supports very large simulation models
- Supports simulation of non-IBM Hardware
- Provides an open framework for simulation of new hardware designs:
    + One neuron per core to thousands of neurons per core
    + Weighted synapses
    + Different spiking neuron models




### NeMo Features
- Implemented using ROSS (Rensselaer's Optimistic Simulation System)
- ROSS provides optimistic and conservative parallel discrete event simulation
- NeMo functions best in optimistic mode
