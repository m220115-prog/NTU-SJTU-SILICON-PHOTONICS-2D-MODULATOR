# 2D and Ferroelectric Photonic Devices

[Back to SJTU research overview](../README.md)

**Stage: experimental characterization**

## Project and contribution

The joint NTU–SJTU project used photonic chips fabricated at NTU, followed by optical and electrical testing at SJTU. The device set included microring resonators and photonic-crystal structures integrated with **graphene/CIPS, black phosphorus/CIPS, and NbOI₂**. Material stacks and electrode geometries were assessed individually when planning bias tests.

My work included writing testing protocols, assembling and aligning the optical measurement setup, recording transmission under electrical excitation, and relating spectra to microscope observations of the transferred materials and photonic structures.

## Measurement workflow

1. Record overview and high-magnification microscope images to inspect material coverage, contacts and waveguide condition.
2. Align the input/output fibers and screen passive transmission before electrical biasing.
3. Apply programmed pulses or stepped DC biases while recording spectra.
4. Compare repeatability, resonance position and transmission changes, then examine possible contributions from coupling drift, contact behaviour and structural damage.

<img width="300" alt="Optoelectronic characterization platform" src="https://github.com/user-attachments/assets/d90b6364-03a2-47c4-b885-67945f9467a3" />

*Optoelectronic characterization setup. Optical fiber alignment and electrical probing were combined for bias-dependent measurements.*

The setup used a tunable laser and optical spectrum measurements, with a RIGOL waveform generator for programmed pulses and a Keithley 2400 source measure unit for DC biasing. Device-protection and polymer-removal steps were considered when setting the measurement order.

Related characterization work included passive free-space testing of grating-coupled lithium-niobate structures, documented in my April 30 meeting record. My [microring project](microring-matrix-computing.md) includes original spectra and a photograph of the electrical/optical testbench.

## Selected measurements

Passive screening identified a BP/CIPS device and an NbOI₂ device with usable transmission for subsequent active measurements. Other structures showed coupling failure or substantial optical loss. The BP device's spectrum was degraded and showed interference features, complicating interpretation of its nominal microring response.

| BP/CIPS device | NbOI₂ device |
| :---: | :---: |
| <img width="350" alt="Optical micrograph of the BP device used for characterization" src="https://github.com/user-attachments/assets/2bcf8079-a72c-41e7-b16d-74f843de0141" /> | <img width="350" alt="Optical micrograph of the NbOI2 device used for characterization" src="https://github.com/user-attachments/assets/fa78162b-2369-4c00-8206-056f71727132" /> |

| Test | Conditions | Observed response |
| --- | --- | --- |
| BP/CIPS pulse tests | Alternating +8 / −8 V pulses; spectra over 1480–1640 nm | Approximately 0.2 dB or less variation in extinction ratio, with no clear systematic resonance shift |
| NbOI₂ pulse tests | Positive/negative 10 V and 20 V excitation | Variations of approximately 0.4 dB or less, without a reproducible switching trend |
| NbOI₂ DC-bias tests | 50–150 V in 25 V steps | No consistent monotonic resonance shift across the applied biases |

The spectra did not resolve repeatable active modulation under these conditions. The small changes could include coupling drift and vibration. These tests motivated closer examination of device integrity, field geometry and optical stability.

| BP/CIPS pulse-series spectra | NbOI₂ pulse-series spectra | NbOI₂ DC-bias spectra |
| :---: | :---: | :---: |
| <img width="270" alt="Measured BP pulse-series transmission spectra" src="https://github.com/user-attachments/assets/fc96abcb-53f9-4bcb-9497-5f24df99cbf6" /> | <img width="270" alt="Measured NbOI2 pulse-series transmission spectra" src="https://github.com/user-attachments/assets/d19447f7-5c06-45d6-a8ee-a0d69f30aee5" /> | <img width="270" alt="Measured NbOI2 spectra under stepped DC bias" src="https://github.com/user-attachments/assets/6e597bd9-fc82-4cea-9a9f-6b4489fc8377" /> |

## Integration and measurement insights

Microscope inspection showed unwanted flakes, residue and visible damage near some photonic structures. These observations suggested transfer contamination and mechanical loading as possible contributors to optical loss and coupling failure. Correlating inspection with transmission helped identify which devices could support further electrical tests.

<img width="650" alt="Microscope inspection of the damaged BP photonic device" src="https://github.com/user-attachments/assets/30b37b58-cb4f-44ce-a047-b1be87435f9f" />

*Post-test optical inspection used to assess damage and material placement around the BP device.*

The work highlighted two practical requirements: preserve the photonic structure during transfer, and verify that the electrode geometry applies the intended electric-field component to the active material. Pulse amplitude alone does not establish polarization reversal in a particular stack.

<details>
<summary>Further characterization planned for devices with reproducible modulation</summary>

The protocol also covered synchronized electrical/optical hysteresis measurements, resonance-position and Q-factor extraction, repeated pulse cycles, zero-bias retention and multilevel optical states. These remain characterization objectives beyond the selected measurements shown above.

</details>
