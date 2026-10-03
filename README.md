# NTU-SJTU-SILICON-PHOTONICS-2D-MODULATOR
# Optoelectronic Characterization of 2D Material-Integrated Silicon Photonic Devices

This repository documents the joint NTU-SJTU research project focused on characterizing novel 2D material-based optical modulators. The silicon photonic chips, featuring micro-ring resonators (MRRs) and photonic crystals, were fabricated at NTU. My primary role at SJTU was to design the testing protocols, build the characterization setup, execute the measurements, and perform deep failure analysis.

The devices are designed based on a Metal-Oxide-Semiconductor (MOS) capacitor configuration, integrated directly onto the silicon nitride (SiN) waveguides. As illustrated in the schematic, the device stack is composed of bottom gold (Au) electrodes, a 2D material active channel (e.g., Graphene, Black Phosphorus, or NbOI₂), a ferroelectric dielectric layer (CIPS), and a top gate electrode. This structure enables efficient field-effect modulation.

<img width="559" height="201" alt="Structure Graphene" src="https://github.com/user-attachments/assets/c02f066d-e8da-40d2-b5e6-7d3379ce504c" />

*Figure 1: Schematic diagram of the hybrid 2D-material-integrated photonic device, showing the MOS-like gated stack configured directly over the SiN waveguide.*

---

### Step 1: Experimental Setup & Test Protocol Design

### 1. Theoretical Framework: Voltage-Dependent Electro-Optic Mechanisms

The electro-optic (EO) modulation in our hybrid 2D-material-integrated device originates from the interplay between two distinct physical mechanisms: the **linear Pockels effect** and **non-linear ferroelectric polarization switching**.

### 1. Theoretical Framework: Voltage-Dependent Electro-Optic Mechanisms

The electro-optic (EO) modulation in our hybrid $NbOI_2$/CIPS-on-SiN device originates from the interplay between two distinct physical mechanisms: the **linear Pockels effect** and **non-linear ferroelectric polarization switching**.

#### 1.1 Linear Pockels Effect & Theoretical Limits
Under an external bias, the non-centrosymmetric $NbOI_2$ layer exhibits a linear Pockels response. The electric-field-induced refractive index change ($\Delta n_{\text{Pockels}}$) is modeled as:
$$\Delta n_{\text{Pockels}} = \frac{1}{2} n^3 r E = \frac{1}{2} n^3 r \left(\frac{V}{d}\right)$$

Where the physical parameters are defined as:
* $n \approx 2.4$: Refractive index of $NbOI_2$ at $\lambda_0 = 1550$ nm.
* $r \approx 8.5 \times 10^{-12}$ m/V: Linear electro-optic (Pockels) coefficient of $NbOI_2$.
* $d \approx 8$ μm: Effective electrical thickness between the top and bottom electrodes.
* $\Gamma \approx 0.10$: Optical mode overlap factor within the active $NbOI_2$ region, pre-calculated via 2D mode-solving simulations (Lumerical MODE).

By accounting for the mode overlap ($\Delta n_{\text{eff}} = \Gamma \Delta n_{\text{Pockels}}$) and a coverage ratio of $1/4$ along the microring waveguide, the theoretical resonance wavelength shift ($\Delta \lambda$) per volt is derived as:
$$\frac{\Delta \lambda}{\Delta V} = \frac{\lambda_0}{n_g} \cdot \frac{\Delta n_{\text{eff}}}{\Delta V} \approx 0.14 \text{ pm/V}$$
*(Note: $n_g \approx 2.0$ represents the group index of the waveguide).* 

This continuous, volatile response is present across all voltage ranges but remains extremely weak, establishing a negligible baseline for active modulation.

#### 1.2 Non-linear Ferroelectric Switching
In contrast, when the applied field exceeds the coercive field ($E_c$) of the CIPS layer, ferroelectric domain switching is triggered, leading to a spontaneous polarization change ($\Delta P$). The resulting refractive index shift is non-volatile and scales quadratically with polarization:
$$\Delta n_{\text{Ferro}} \propto P^2$$
This mechanism delivers an abrupt, order-of-magnitude larger refractive index leap, enabling robust non-volatile optical memory states.

#### 1.3 Voltage Regimes & Transition Dynamics
Based on the coercive threshold of the CIPS layer, the device operation is divided into three distinct regimes:

1. **Sub-Coercive Regime (0 – 7 V):**
   The electric field is below the switching threshold ($E < E_c$). The ferroelectric domains remain clamped, and the device response is dominated solely by the weak, linear Pockels baseline ($\sim 0.14 \text{ pm/V}$).
   
2. **Ferroelectric Switching Regime (7 – 14 V) — Core Study Area:**
   The applied voltage overcomes the coercive field, initiating rapid domain reversal in CIPS. The dramatic shift in polarization ($\Delta P$) yields a giant, hysteretic wavelength shift with non-volatile retention, which serves as the foundation for our memory modulator.

3. **Saturation Regime (> 14 V):**
   The ferroelectric polarization reaches saturation ($P = P_{\text{sat}}$). Beyond this threshold, no further domain reorientation can occur ($\Delta P = 0$), and the incremental optical response reverts to the weak, linear Pockels slope superimposed on the saturated state.






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


