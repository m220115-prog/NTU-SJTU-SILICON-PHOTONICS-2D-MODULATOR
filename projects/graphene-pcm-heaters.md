# Graphene Heaters for Phase-Change Photonics

[Back to SJTU research overview](../README.md)

## Project and contribution

This collaborative SJTU project investigated graphene heaters for electrically addressing Sb–Se phase-change material on photonic waveguides. My contribution included graphene wet transfer, active electrical/optical testing and work on electrode-layout redesign following heater failure.

The objective was to deliver heat to the phase-change region while maintaining an electrically continuous graphene path and usable optical transmission.

## Experimental work

- Transferred graphene onto the photonic-device platform using a wet-transfer process.
- Performed electrical checks and active tests to investigate the response under applied voltage or pulses.
- Examined heater failure and discussed revisions to the contacts and patterned geometry.

A representative low-bias check gave approximately **60 μA at 1 V**, corresponding to a total device resistance of approximately **16.7 kΩ** and an electrical input power of approximately **60 μW**. This operating-point estimate helped frame the power budget for heater analysis.

## Electrode layout and power distribution

The patterned current path contains two metal/graphene contact regions, tapered transitions and a narrow central heating section. Applied voltage is distributed across the entire path, so the central region receives only part of the total electrical dissipation.

For a simplified series-resistance model,

$$
R_{\mathrm{tot}} = R_{\mathrm{c1}} + R_{\mathrm{a1}} + R_{\mathrm{h}} + R_{\mathrm{a2}} + R_{\mathrm{c2}},
$$

where the contact terms are R<sub>c1</sub> and R<sub>c2</sub>, the graphene access/taper terms are R<sub>a1</sub> and R<sub>a2</sub>, and R<sub>h</sub> represents the intended heating section. At a common series current,

$$
P_{\mathrm{h}} = I^2R_{\mathrm{h}}, \qquad
\frac{P_{\mathrm{h}}}{P_{\mathrm{tot}}} = \frac{R_{\mathrm{h}}}{R_{\mathrm{tot}}}.
$$

This ratio estimates the fraction of electrical power dissipated in the selected graphene section. The temperature reached by the phase-change material also depends on heat flow through the surrounding structure.

| Design consideration | Engineering question |
| --- | --- |
| Metal/graphene contact | How much voltage drops at the contacts, and how does transfer quality affect that contribution? |
| Contact width and overlap | Can contact geometry reduce unwanted series resistance while preserving fabrication reliability? |
| Taper and access regions | How do the transitions distribute current and add resistance outside the intended heater? |
| Central graphene section | Where is electrical power generated relative to the phase-change region? |
| Transfer residue and continuity | Are contamination, tears or imperfect adhesion contributing to high resistance and failure? |

These considerations guided the redesign discussion. Geometry changes and process improvements were treated as proposals to be evaluated experimentally.

## Research perspective

This work connected material transfer, contact engineering and thermal actuation in an integrated photonic device. It developed my approach to failure analysis: use electrical measurements to constrain the current path, relate the layout to where power is dissipated, and evaluate the resulting optical response.
