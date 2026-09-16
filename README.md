# NTU-SJTU-SILICON-PHOTONICS-2D-MODULATOR
# Optoelectronic Characterization of 2D Material-Integrated Silicon Photonic Devices

This repository documents the joint NTU-SJTU research project focused on characterizing novel 2D material-based optical modulators. The silicon photonic chips, featuring micro-ring resonators (MRRs) and photonic crystals, were fabricated at NTU. My primary role at SJTU was to design the testing protocols, build the characterization setup, execute the measurements, and perform deep failure analysis.

The devices are designed as capacitor-like structures integrated directly over the silicon waveguides. The stack consists of a bottom electrode, a 2D material active channel (Graphene, Black Phosphorus, or NbOI₂), a ferroelectric dielectric layer (CIPS), and a top gate electrode.

<img width="720" height="365" alt="Structure Graphene" src="https://github.com/user-attachments/assets/b7bd77d2-1032-4cc5-8740-ab3b52b3de42" />


*Figure 1: Schematic of the 2D material-integrated photonic device, illustrating the capacitor-like structure (Bottom Electrode / 2D Channel / CIPS / Top Gate) over a silicon waveguide.*

---

### Step 1: Experimental Setup & Test Protocol Design

To perform high-fidelity optoelectronic characterization, I built a custom four-probe station integrated with external optical and electrical equipment.

**Testbed Construction:** The setup utilizes four probes: two optical probes for fiber-to-chip light coupling (input/output) and two electrical probes for applying pulses to the device electrodes. The station is connected to a spectrometer, a tunable pulse voltage source, an oscilloscope, and a backup current source. I selected the voltage source for active testing not only for its fast switching speed (critical for generating short pulses) but also for its ability to provide larger driving voltages (up to 10V) compared to the current source.

**Test Protocol Design:** I independently designed the entire characterization sequence. Instead of simple sweeps, the core of the active testing was designed around cyclic pulse measurements. The protocol involved applying a specific programming voltage pulse to polarize the ferroelectric CIPS layer, followed by a reading phase to record the transmission spectrum. By extracting the resonance wavelength shift (Δλ₀) and changes in the peak intensity and Q-factor over multiple cycles, the goal was to quantify the non-volatile memory effects. The physical mechanism behind this design relies on the principle that the change in the effective refractive index (Δn) is proportional to the square of the ferroelectric polarization (Δn ∝ P²).

<!-- 💡 操作提示：这里放您搭台子的照片 -->
<img width="500" alt="Test Setup" src="这里放测试平台照片的链接" />

*Figure 2: The custom-built four-probe optoelectronic characterization setup.*

---

### Step 2: Passive Screening & Structural Integrity

Before active testing, I performed passive spectral measurements on all devices to check their basic optical functionality post-transfer. 

The screening criteria went beyond simply finding a resonance peak. I specifically checked if the **number of peaks** and the **Free Spectral Range (FSR, the distance between peaks)** matched the theoretical design. 

If the peaks were completely missing, or if the FSR was severely distorted, it indicated that light was no longer propagating through the designed optical path. Through microscopic inspection, I identified several root causes for these passive failures:
1. **Severe Contamination:** Heavy residues from the dry transfer process completely blocked the optical pathways.
2. **Mechanical Damage:** The excessive mechanical pressure applied during the dry transfer process physically crushed the fragile silicon photonic structures (MRRs and waveguides).

---

### Step 3: Active Testing & Sequential Failures

For the devices that survived the passive screening, I proceeded with the active cyclic testing. However, the initial testing round revealed a series of sequential failures.

**Round 1: Graphene and Black Phosphorus (BP) Devices**
I first applied the active testing protocol to the Graphene and BP devices. Both sets of devices failed to show the expected non-volatile spectral modulation. The data revealed a complete absence of the designed memory window.

<!-- 💡 操作提示：放 Graphene 和 BP 有源测试失败的图 -->
<img width="500" alt="Graphene and BP Active Failure" src="这里放 Graphene 和 BP 失败的数据图链接" />
*Figure 3: Active testing results for Graphene and BP devices, showing a complete lack of expected ferroelectric memory modulation.*

**Process Intervention: PMMA Removal**
Because the chips were shipped from NTU in a vacuum with a protective PMMA layer specifically coating the NbOI₂ flakes, I had to soak the entire chip in acetone to strip the PMMA before testing the NbOI₂ devices. Unfortunately, this necessary solvent soaking process completely destroyed the remaining Graphene and BP structures, as they lacked protective coatings and were highly sensitive to solvents.

**Round 2: NbOI₂ Devices**
After the acetone soak, I conducted the active cyclic tests on the NbOI₂ devices. These devices also failed to exhibit the target optoelectronic modulation.

<!-- 💡 操作提示：放 NbOI2 有源测试失败的图 -->
<img width="500" alt="NbOI2 Active Failure" src="这里放 NbOI2 失败的数据图链接" />
*Figure 4: Active testing results for the NbOI₂ devices post-acetone soak, yielding similar non-functional optical responses.*

---

### Step 4: Failure Analysis & Device Recycling Attempt

After analyzing the complete failure of this batch, it became clear that the transfer process contamination and mechanical damage were fatal. 

**Attempting Chip Recycling:**
Silicon photonics nano-fabrication is highly resource-intensive, with a single fabrication cycle from design to completion taking nearly a month. To save time, I attempted to recycle these failed chips instead of waiting for a new batch. My plan was to strip away all the transferred 2D materials and residues using a high-power, long-duration plasma cleaning process, hoping to expose the pristine silicon waveguides underneath.

**Result and Feedback:**
The recycling attempt failed. Even after prolonged plasma exposure, the chips remained excessively dirty under the microscope. The likely reason is that the polymeric residues from the transfer stamps underwent cross-linking and hardened under the intense plasma heat, or they contained inorganic contaminants that standard oxygen/argon plasma chemistry could not etch away. 

Consequently, I documented these failure mechanisms and shipped the batch back to NTU, providing critical feedback to refine the dry transfer pressure parameters and cleanliness protocols for the next fabrication cycle.


