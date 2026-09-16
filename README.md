# NTU-SJTU-JOINT-PROGRAM-ZHANG-JINMING
# Optoelectronic Characterization of 2D Material-Integrated Silicon Photonic Devices

This repository documents the joint NTU-SJTU research project focused on the characterization of novel 2D material-based optical modulators. The silicon photonic chips, featuring micro-ring resonators (MRRs) and photonic crystals, were fabricated at NTU. My primary role at SJTU was to lead the entire testing workflow: from designing the characterization protocol and building the test setup, to analyzing the final device performance and troubleshooting experimental failures.

The devices under test are capacitor-like structures where 2D materials (Graphene, Black Phosphorus, or NbOI₂) are integrated as active channels on top of a ferroelectric dielectric (CIPS) and a bottom electrode.

<!-- 💡 操作提示：这里放您提到的器件结构示意图 -->
<img width="500" alt="Device Schematic" src="这里放器件示意图的链接" />

*Figure 1: Schematic of the 2D material-integrated photonic device, forming a capacitor structure over a silicon waveguide.*

---

### Step 1: Experimental Setup & Test Protocol Design

To perform high-fidelity optoelectronic characterization, a custom four-probe station was built and integrated with external equipment.

*   **Testbed Construction**: The setup utilizes four probes: two for optical I/O (fiber-to-chip coupling) and two for applying electrical pulses to the device electrodes. The station is connected to a spectrometer, a tunable pulse voltage source, an oscilloscope, and a backup current source. The voltage source was chosen for active testing due to its faster switching speed, which is critical for applying short pulses.
*   **Test Protocol Design**: I independently designed the entire characterization protocol, covering everything from initial passive validation to active-duty cycling and endurance tests. The test plan (detailed in the original [planning slides](这里可以链接您的PPT文件)) was structured to systematically quantify key performance metrics like resonance shift (Δλ₀), Q-factor, and non-volatile memory effects based on the underlying device physics, where the change in refractive index (Δn) is proportional to the square of the ferroelectric polarization (Δn ∝ P²).

<!-- 💡 操作提示：这里放您测试平台（“搭台子”）的照片 -->
<img width="500" alt="Test Setup" src="这里放测试平台照片的链接" />

*Figure 2: The custom-built four-probe optoelectronic characterization setup.*

---

### Step 2: Device Characterization & Troubleshooting

The testing workflow was executed in several phases, encountering and resolving critical issues along the way.

#### 2.1. Initial Passive Screening

Before active testing, a passive spectral measurement was performed on all devices to check for basic functionality post-transfer. The key was to observe the transmission spectrum: a preserved resonance peak, even if shifted or broadened, indicated a working device.

#### 2.2. Troubleshooting: Material & Process-Induced Failures

During the initial testing round, I identified two major failure modes:

*   **Problem 1: Material Degradation.** The initial plan involved soaking the chips in acetone to remove the PMMA protective layer from the NbOI₂ flakes. However, this process completely destroyed the other two materials (Black Phosphorus and Graphene), which were not PMMA-coated and are highly sensitive to solvents.
*   **Problem 2: Contamination & Waveguide Blockage.** Many devices showed poor or no optical transmission. Microscopic inspection revealed that this was caused by residue from the dry transfer process, which physically blocked the optical path of the waveguides. Pressing too hard during transfer also sometimes damaged the underlying fragile photonic structures.

<!-- 💡 操作提示：这里可以放一张“很脏”或“压坏了”的显微镜照片 -->
<img width="400" alt="Device Failure" src="这里放一张失效器件的图片链接" />

*Figure 3: Optical micrograph of a failed device, showing transfer-induced contamination obscuring the waveguide.*

#### 2.3. Corrective Action & Process Feedback

Based on the failure analysis, I provided the following feedback to the fabrication team at NTU:

*   **Process Refinement**: To address the contamination, a plasma cleaning step was introduced. However, even after prolonged plasma exposure, some residues remained, likely due to their polymeric nature being resistant to the specific plasma chemistry used. This led to the decision to ship the problematic batch of chips back to NTU for more advanced cleaning and re-fabrication. This iterative troubleshooting loop was crucial for improving the device yield.

<!-- 💡 操作提示：这里可以放一张等离子清洗设备（Plasma Cleaner）的照片 -->
<img width="400" alt="Plasma Cleaner" src="这里放Plasma设备的照片链接" />

*Figure 4: The PIE Scientific Tergeo Plasma Cleaner used in an attempt to remove transfer residues.*

---

### Step 3: Active Device Performance (Non-Volatile Memory)

For the successfully fabricated devices, I proceeded with active testing to validate the non-volatile memory effect. By applying voltage pulses to polarize the ferroelectric CIPS layer, I observed a clear and repeatable shift in the spectral resonance, confirming the non-volatile modulation of the device's optical properties. The data below shows a typical result from a working device, demonstrating its potential as an optical memristor.

<!-- 💡 操作提示：从您PPT里挑选最能代表“有源测试成功”的数据图，比如光谱移动或Q因子变化图 -->
<img width="500" alt="Active Modulation" src="这里放一张有源测试成功的数据图链接" />

*Figure 5: Non-volatile spectral shift in a working device. The resonance peak (transmission dip) remains at different wavelengths after applying SET and RESET voltage pulses, demonstrating the memory effect.*

