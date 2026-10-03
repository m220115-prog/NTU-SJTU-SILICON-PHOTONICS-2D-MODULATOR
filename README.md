# NTU-SJTU-SILICON-PHOTONICS-2D-MODULATOR
## Optoelectronic Characterization of 2D Material-Integrated Silicon Photonic Devices

This repository documents the joint NTU-SJTU research project focused on characterizing novel 2D material-based optical modulators. The silicon photonic chips, featuring micro-ring resonators (MRRs) and photonic crystals, were fabricated at NTU. My primary role at SJTU was to design the testing protocols, build the characterization setup, execute the measurements, and perform deep failure analysis.

The devices are designed based on a Metal-Oxide-Semiconductor (MOS) capacitor configuration, integrated directly onto the silicon nitride (SiN) waveguides. As illustrated in the schematic, the device stack is composed of bottom gold (Au) electrodes, a 2D material active channel (e.g., Graphene, Black Phosphorus, or NbOI₂), a ferroelectric dielectric layer (CIPS), and a top gate electrode. This structure enables efficient field-effect modulation.

<img width="559" height="201" alt="Structure Graphene" src="https://github.com/user-attachments/assets/c02f066d-e8da-40d2-b5e6-7d3379ce504c" />

*Figure 1: Schematic diagram of the hybrid 2D-material-integrated photonic device, showing the MOS-like gated stack configured directly over the SiN waveguide.*

## Experimental Setup & Characterization Methodology

### Testbed Construction and Instrumentation

The optoelectronic characterization platform uses a four-probe station. Two optical fiber probes align to the chip facets to couple light into and out of the waveguides. Two electrical tungsten probes make contact with the coplanar gold pads on the device. The platform connects to a tunable laser and an optical spectrum analyzer.

*Figure 2: Schematic Diagram of the Optoelectronic Testbed*

*Figure 3: Photograph of the Physical Four-Probe Station Setup*

Electrical excitation is supplied by two separate sources. The RIGOL DG4202 arbitrary waveform generator outputs voltage pulses up to 10 V with transition times under 5 ns. Its advantage is automated microsecond pulse programming without manual triggering errors. The Keithley 2400 Source Measure Unit provides a wide voltage output range up to 200 V and high precision current measurement. It is used for high-voltage DC characterization.

### Passive Optical Screening and Device Health Status

Passive optical transmission was measured across all fabricated waveguides on the chip before conducting active electrical tests. Transverse electric polarized light was swept from 1480 nm to 1640 nm.

Most devices on the chip were damaged during the material transfer process and could not couple light. Only one black phosphorus device and one $\text{NbOI}_2$/CIPS hybrid device remained transmissive.

The black phosphorus device is damaged. Its transmission shows that the microring resonance is degraded into Fabry-Perot cavity resonance with shifted peak positions and altered free spectral range. The $\text{NbOI}_2$/CIPS device is also partially damaged and exhibits high insertion loss along the ring boundary.

The experimental testing sequence is determined by material protection requirements. Low-dimensional materials oxidize rapidly in ambient air. In addition to vacuum packaging, the $\text{NbOI}_2$/CIPS device was spin-coated with a protective polymethyl methacrylate layer. Removing this polymer requires an acetone wash. Acetone washing will permanently damage all exposed adjacent devices including the black phosphorus flake. Therefore, all passive and active measurements on the black phosphorus device are conducted first. Chemical deprotection is performed afterward to expose the coplanar electrodes of the $\text{NbOI}_2$/CIPS device.


### Theoretical Framework and Active Modulation Mechanisms

Active modulation characterization is primarily focused on the surviving $\text{NbOI}_2$/CIPS device. The black phosphorus device was also measured under active bias for comparative analysis.

Modulation in the hybrid device combines the linear Pockels effect and interfacial ferroelectric gating. Symmetrical coplanar gold electrodes sit on both sides of the SiN waveguide with a lateral gap spacing $g$ of 8 $\mu\text{m}$. This lateral configuration prevents metal absorption loss.

An applied bias creates a lateral electric field $E = V/g$. This field modifies the refractive index of the $\text{NbOI}_2$ layer:

$$\Delta n_{\text{Pockels}} = \frac{1}{2} n^3 r E = \frac{1}{2} n^3 r \frac{V}{g}$$

At 1550 nm, $\text{NbOI}_2$ has a refractive index $n \approx 2.4$ and a linear Pockels coefficient $r \approx 8.5 \times 10^{-12}\ \text{m/V}$. Optical simulations give a mode overlap factor $\Gamma \approx 0.10$ in the active region. The material covers one quarter of the microring circumference. The theoretical resonance wavelength shift per volt is:

$$\frac{\Delta \lambda}{\Delta V} = \frac{\lambda_0}{n_g} \frac{\Delta n_{\text{eff}}}{\Delta V} \approx 0.14\ \text{pm/V}$$

Here $n_g \approx 2.0$ is the group index of the waveguide.

Although both $\text{NbOI}_2$ and CIPS possess ferroelectric properties, their operational roles differ fundamentally due to their distinct spontaneous polarization orientations. $\text{NbOI}_2$ is an in-plane ferroelectric material where the spontaneous polarization aligns laterally within the 2D plane. In this device configuration, $\text{NbOI}_2$ serves as the non-centrosymmetric optical channel to supply the fast linear Pockels electro-optic response, rather than acting as a non-volatile gating medium. In contrast, CIPS is an out-of-plane ferroelectric material with spontaneous polarization oriented vertically perpendicular to the layers. The vertical polarization reversal in CIPS generates high-density surface bound charges directly across the van der Waals interface, providing strong electrostatic gating to switch the optical transmission states.

Based on experimental polarization-voltage hysteresis data of CIPS, the coercive voltage $V_c$ is 1.5 V and the saturation voltage $V_{\text{sat}}$ is 4.5 V.

<img width="312" height="220" alt="Polarization-Voltage Hysteresis Loop of CIPS" src="https://github.com/user-attachments/assets/d30cac0c-4a87-4e4c-9460-49890c827ef0" />

*Figure 4: Polarization-Voltage Hysteresis Loop of CIPS with Coercive and Saturation Thresholds*

These threshold voltages divide the device operation into three distinct regimes.

In the sub-coercive regime from 0 V to 1.5 V, the electric field remains below the coercive threshold $V_c$. The ferroelectric domains do not switch, and the optical response follows the weak linear Pockels baseline.

In the ferroelectric switching regime from 1.5 V to 4.5 V, the external electric field switches the CIPS layer between its two stable remnant polarization states, $+1$ and $-1$. These opposing polarization states induce opposite electrostatic surface charges at the interface. This electrostatic gating directly shifts the Fermi level and modulates carrier concentration in the underlying 2D channel layer, switching the device between state 1 with high optical transmission and state 0 with low optical transmission. Operating between these two saturated remnant polarizations provides stable, non-volatile optical memory states while avoiding the instability of intermediate unpolarized states.

In the saturation regime above 4.5 V, the spontaneous ferroelectric polarization reaches its saturation limit. The accumulated interface charge remains constant, and no further polarization switching occurs. The optical response in this high-field regime is governed solely by the linear Pockels effect superimposed on the saturated background.

### Active Characterization Results: Black Phosphorus Device

Active electro-optic characterization was first conducted on the surviving black phosphorus device.

<img width="600" height="428" alt="BP213" src="https://github.com/user-attachments/assets/2bcf8079-a72c-41e7-b16d-74f843de0141" />

*Figure 5: Optical Microscope Image of Black Phosphorus Device*

The measurement protocol applied automated cyclic electrical pulses using a driving voltage of 8 V. Based on the coercive field requirements, an amplitude of 8 V is theoretically sufficient to complete both the set and reset polarization processes across the active channel. The excitation sequence cycled repeatedly between positive 8 V and negative 8 V pulses to evaluate reversible optical switching.

<img width="317" height="343" alt="BP cycle test" src="https://github.com/user-attachments/assets/fc96abcb-53f9-4bcb-9497-5f24df99cbf6" />

*Figure 6: Ferroelectric Pulse Cycle Transmission Spectra and Zoomed Resonance Dip of BP Device*

Optical transmission was recorded across the telecommunication band from 1480 nm to 1640 nm. The detailed zoom-in region around the resonance dip near 1550 nm tracks the spectral shift across multiple alternating set and reset pulses.

The measured transmission curves show negligible electro-optic modulation. Across repeated cycles under positive and negative 8 V pulses, the maximum variation in extinction ratio remains within 0.2 dB. The resonance dip position exhibits no observable wavelength shift. In this experimental setup, an optical variation below 0.2 dB falls within the baseline noise margin of optical fiber probe coupling and platform vibration. Therefore, this variation cannot be attributed to genuine electro-optic or ferroelectric switching and must be classified as measurement error.

### Active Characterization Results: NbOI<sub>2</sub> Device

Active electro-optic characterization was subsequently conducted on the surviving $\text{NbOI}_2$/CIPS device, following acetone deprotection of the sacrificial polymethyl methacrylate layer.

<img width="340" height="328" alt="NbOI2" src="https://github.com/user-attachments/assets/fa78162b-2369-4c00-8206-056f71727132" />

*Figure 7: Optical Microscope Image of NbOI<sub>2</sub> Device*

Two sets of electrical excitation experiments were carried out on this device. The first experiment evaluated non-volatile ferroelectric switching using larger pulse amplitudes of positive and negative 10 V and 20 V. Higher amplitudes above the coercive threshold were chosen to guarantee complete domain reversal.

<img width="258" height="344" alt="NbOI2 cycle test" src="https://github.com/user-attachments/assets/d19447f7-5c06-45d6-a8ee-a0d69f30aee5" />


*Figure 8: Ferroelectric Pulse Cycle Transmission Spectra and Zoomed Resonance Dip of NbOI<sub>2</sub> device*

Optical transmission was recorded from 1480 nm to 1640 nm, with detailed inspection centered at the transmission dip near 1550 nm. The measured spectra show no distinct ferroelectric switching response. Across all five voltage steps, the maximum variation in extinction ratio remains within 0.4 dB. The transmission dip exhibits random fluctuations rather than systematic red-shifts or blue-shifts. In this testing environment, an amplitude change within 0.4 dB and random peak shifts fall within the limits of optical coupling drift and stage vibration. Consequently, these variations are attributed to system measurement error rather than physical ferroelectric polarization switching.

The second experiment investigated the linear Pockels electro-optic response using the Keithley 2400 source measure unit in high-voltage DC mode. Static DC bias was stepped from 50 V to 150 V with a step size of 25 V to observe field-induced linear refractive index changes.

<img width="258" height="351" alt="NbOI2 high V" src="https://github.com/user-attachments/assets/6e597bd9-fc82-4cea-9a9f-6b4489fc8377" />

*Figure 9: High-Voltage DC Transmission Spectra and Zoomed Resonance Dip of NbOI<sub>2</sub> device*

The transmission curves across the voltage progression from 50 V to 150 V show no consistent linear electro-optic modulation. The maximum difference in extinction ratio across all voltage levels remains approximately 0.4 dB. The resonance dip does not follow a monotonic linear wavelength shift per volt. Because the optical response displays no regular trend and stays within the 0.4 dB coupling uncertainty threshold, the high-voltage test does not produce a measurable linear Pockels effect.

### Failure Analysis and Fabrication Insights

Optical microscope inspection after testing reveals two primary causes for device failure and excessive optical loss.

The first issue originates from surface contamination during the dry transfer process. Dry transfer lacks spatial selectivity. Transferring exfoliated 2D flakes onto specific target areas inevitably leaves unwanted material fragments and polymer residue across adjacent structures. Because these 2D crystals have high refractive indices, stray flakes directly perturb the optical mode and introduce severe scattering loss. This extensive contamination along the waveguides explains the elevated insertion loss across the surviving devices.

The second issue stems from excessive mechanical pressure during stamping. The dry transfer protocol requires mechanical contact to press the transfer elastomer against the chip surface. Microscope inspection indicates that multiple photonic structures suffered mechanical destruction during this contact step. Optical coupling channels and bus waveguides were fractured or crushed by the applied pressure. This structural damage directly explains why most devices failed initial passive optical coupling. Furthermore, mechanical pressing damaged the ring cavity boundary on the black phosphorus device, causing the observed collapse of microring resonance into an irregular Fabry-Perot interference cavity.

<img width="850" height="604" alt="destroyed BP" src="https://github.com/user-attachments/assets/30b37b58-cb4f-44ce-a047-b1be87435f9f" />

*Figure 10: Optical Microscope Image of Mechanically Damaged Black Phosphorus Device*

### Appendix: Planned Characterization Protocol

A full experimental protocol was designed before testing. This plan refers to recent literature on 2D ferroelectric optical modulators. It outlines the systematic steps to verify device behavior once clean fabrication is achieved. Because the initial cycle showed no active modulation due to transfer damage, subsequent steps were halted. The full testing logic is preserved below.

The first step takes microscope photos. A low-magnification photo records the overall device layout and electrode pads. A high-magnification photo inspects flake coverage and waveguide alignment.

<img width="774" height="296" alt="高倍镜和低倍镜" src="https://github.com/user-attachments/assets/bbc626b1-5215-4438-8d2d-bc75964cb0fe" />

*Figure 11: Target Optical Microscope Photos at Low and High Magnification*

The second step measures basic single-cycle and multi-cycle responses. The gate voltage sweeps continuously between negative 8 V and positive 8 V. Optical transmission at the 1550 nm telecommunication wavelength is measured synchronously during the voltage sweep alongside channel current. Then, pulsed voltage trains are applied to record optical transmission over time at 1550 nm across multiple cycles.

<table>
  <tr>
    <td align="center"><img width="361" height="276" alt="WechatIMG2218" src="https://github.com/user-attachments/assets/9c9b1eb0-fe8a-4ee2-9059-5e0591ccb775" /></td>
    <td align="center"><img width="357" height="276" alt="WechatIMG2219" src="https://github.com/user-attachments/assets/a6415e99-a5d8-437e-add8-c9b6a8ee5654" /></td>
  </tr>
  <tr>
    <td align="center"><i>Figure 12: Single-cycle optical transmission at 1550 nm and channel current (I<sub>ds</sub>) hysteresis loops.</i></td>
    <td align="center"><i>Figure 13: Dynamic Set/Reset pulse response showing time-resolved optical transmission switching.</i></td>
  </tr>
</table>

The third step maps spectral shifts. Transmission spectra are recorded across the telecommunication band under different voltages. Resonance dip shifts and cavity quality factors are extracted and plotted against voltage to track cavity loss changes.

<table>
  <tr>
    <td align="center"><img width="502" height="217" alt="WechatIMG2220" src="https://github.com/user-attachments/assets/2f69842c-2c8d-4de5-bdf2-8ca52d78fca2" /></td>
    <td align="center"><img width="231" height="196" alt="WechatIMG2221" src="https://github.com/user-attachments/assets/9cb80671-28ce-4c47-9380-637a054605e5" /></td>
    <td align="center"><img width="252" height="200" alt="WechatIMG2222" src="https://github.com/user-attachments/assets/b29fcb1f-95b7-4884-b650-7e064ecee327" /></td>
  </tr>
  <tr>
    <td align="center"><i>Figure 14: Gate-tunable broadband resonance shifts across 1520–1580 nm under discrete V<sub>G</sub> states.</i></td>
    <td align="center"><i>Figure 15: Multi-wavelength resonance wavelength shift (Δλ<sub>0</sub>) hysteresis confirming tuning reversibility.</i></td>
    <td align="center"><i>Figure 16: Gate-voltage-dependent Q-factor tuning hysteresis at multi-wavelengths.</i></td>
  </tr>
</table>

The fourth step evaluates switching endurance and retention. Alternating set and reset pulses at 8 V repeat over multiple cycles to track transmission stability at 1550 nm. Following a single pulse, transmission is recorded over extended idle time at zero bias to evaluate non-volatile storage stability.

<table>
  <tr>
    <td align="center"><img width="397" height="224" alt="WechatIMG2223" src="https://github.com/user-attachments/assets/ad9ddc92-3037-4913-80b4-83eb90fca4c5" /></td>
    <td align="center"><img width="390" height="227" alt="WechatIMG2224" src="https://github.com/user-attachments/assets/f5722f9e-a5f7-4c46-9db5-d22e2693ce1f" /></td>
  </tr>
  <tr>
    <td align="center"><i>Figure 17: 400-cycle Set/Reset endurance at 1550 nm demonstrating a stable memory window.</i></td>
    <td align="center"><i>Figure 18: Zero-bias optical retention stability extrapolated to 10 years (24-hour measured baseline).</i></td>
  </tr>
</table>

The final step tests multi-level state storage. Transmission spectra are compared between opposite saturated states. Variable pulse amplitudes between 0 V and 10 V are applied to record intermediate transmission levels for multi-bit optical memory.

<table>
  <tr>
    <td align="center"><img width="377" height="217" alt="WechatIMG2225" src="https://github.com/user-attachments/assets/290fb1b8-191c-4387-be40-63d328393771" /></td>
    <td align="center"><img width="458" height="249" alt="WechatIMG2226" src="https://github.com/user-attachments/assets/ba93339a-6263-447f-aae8-1f96aeb9ec58" /></td>
  </tr>
  <tr>
    <td align="center"><i>Figure 19: Broadband (1500–1600 nm) transmission envelope contrast between saturated Set and Reset states.</i></td>
    <td align="center"><i>Figure 20: Multi-level optical weight storage plateaus via incremental Set pulses (analog memristive behavior).</i></td>
  </tr>
</table>

All reference figures in this section are adapted from Y. Zhang et al., “On-chip optical memristors based on ferroelectric-doped graphene,” Optica, vol. 12, no. 1, pp. 88–98, Jan. 2025.
