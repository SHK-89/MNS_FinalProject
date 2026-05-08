# Sharp Wave Ripples in a Bistable Network

This mini project simulates **sharp wave-ripple complexes (SWRs)** in a simplified hippocampal CA3 network model. The project was developed for the *Models of Neural Systems – Computer Practical* course at BCCN Berlin.

SWRs are short, highly synchronized hippocampal events that typically last around 50–100 ms and are associated with memory consolidation during slow-wave sleep and quiet wakefulness. In this project, we reproduce and analyze a proposed disinhibition-based mechanism for SWR generation.

## Project Overview

The model contains three interacting neuronal populations:

- **Pyramidal cells (P)**: excitatory neurons
- **PV+ basket cells (B)**: inhibitory interneurons
- **Anti-SWR cells (A)**: inhibitory interneurons that suppress SWR activity in the non-SWR state

The key idea is that SWRs can emerge through a **disinhibition mechanism**. In the non-SWR state, anti-SWR cells inhibit pyramidal and basket-cell activity. As the synaptic efficacy from basket cells to anti-SWR cells changes over time, inhibition of the anti-SWR population increases, releasing pyramidal and basket cells from inhibition and allowing the network to enter an SWR state. Short-term synaptic depression then terminates the event and returns the system to the non-SWR state.

## Main Goals

The project aims to:

1. Implement a spiking neural network model of SWR generation.
2. Demonstrate bistability between SWR and non-SWR network states.
3. Simulate spontaneous SWR events.
4. Estimate a local field potential-like signal from synaptic currents.
5. Detect and quantify SWR events.
6. Compare simulated SWR statistics with findings reported in the literature.

## Methods

The simulation uses:

- Leaky integrate-and-fire neuron models
- Conductance-based synapses
- Sparse connectivity between neuronal populations
- Short-term synaptic depression in the B → A synapse
- Population firing-rate analysis
- LFP-like signal estimation from synaptic currents
- Signal filtering and peak detection
- Statistical analysis of SWR properties

The main analysis includes:

- State-switching experiments with externally injected currents
- Spontaneous SWR simulation with unclamped synaptic efficacy
- Detection of SWR event boundaries
- Calculation of inter-event intervals (IEIs)
- Calculation of event duration and incidence
- Power spectral density analysis
- Correlation analysis between SWR amplitude and previous/next IEI

## Results Summary

The project successfully reproduced several important qualitative and quantitative features of the reference model:

- The network showed **bistability**, switching between non-SWR and SWR states.
- Spontaneous SWR events emerged when the B → A synaptic efficacy was allowed to evolve dynamically.
- Simulated SWR events showed properties in a biologically plausible range.
- SWR incidence was approximately **1.0–1.55 events/s**.
- The average event duration was approximately **106.67 ms**.
- A strong correlation was observed between SWR amplitude and the **previous** inter-event interval.
- The correlation between SWR amplitude and the **next** inter-event interval was weak.

These findings support the idea that a disinhibition-based bistable network can reproduce several properties of hippocampal SWRs.
