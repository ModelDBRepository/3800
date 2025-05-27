# Version 2002-08-30 Temperature sensitivity changed: (Behavior unchanged at 27 C)

Ingemar Jacobson contributed this model with the comment
"... Following compilation the model can be launched from the startatrial1.hoc file - you then just need to start the simulation - I suggest with the variable time step ticked. I had some problems with the intracellular Ca2+-dynamics and for clarity I had to split it into several files - now it works reasonably well also for CVODE. Having defined the model files of the various cardiac currents it is an easy task to convert the atrial model to more or less any other cardiac cell type. Hopefully this will be of some use for cardiac electrophysiogists. ..."

and also
"... Perhaps some of the model files can serve as templates for neuronal channels- the molecular correlate for the cardiac Ito is Kv4.3, for IKur it is Kv1.5; for IKr - it is HERG, all these being potassium channels you will find in the CNS. ..."

Questions about the model should be directed to the original authors.
Questions about the computer implementation should be directed to Dr. Jacobson. Questions about the database presentation should be directed to Michael Hines. Following is a slightly expanded copy of the "about" screen that pops up when the model is executed. Running the model via the mosinit.hoc file (executed automatically by the autolaunch process) will generate the heart action potential shown in the ap.gif file.

---

The Virtual Human Atrial Cell is assembled for NEURON by
Ingemar Jacobson
AstraZeneca R & D, Mölndal Sweden
emailaddress ingemar.jacobson@astrazeneca.com

The model is based on the paper by

Marc Courtemanche, Rafael J. Ramirez, and Stanley Nattel.
Ionic mechanisms underlying human atrial action potential properties
insights from a mathematical model
*Am J Physiol Heart Circ Physiol* 1998 275: H301-H321.

and conductance values are adjusted to give appropriate current densities. Pumps, exchangers and an additional electroneutral ion accumulation mechanism are sat so that ion concentrations are stable at a pacing rate of 1 Hz.

The kinetics of IKur is modified to fit data of Feng et al
*Am J Physiol* 1998 275(Heart Circ Physiol 44):H1717-H1725.

The possibility to include a nonspecific cation-current with kinetics similar to IKur is also given in the IKur mechanism. For the intracellular Ca dynamics to work the mechanisms Cadynam, ca_jsr, Ca_jsracc and ca_nsracc have to be inserted. For simulation of intracellular Na+-ion and K+-ion changes the mechanisms Na_acc and K_acc have to be inserted. The model is free to use provided acknowledgement is given to the developers of NEURON.

- nseg = 1
- L = 100 um
- diam = 16 um
- cm = 2 uF/cm²
- Vi - intracellular volume 13668 um³

- SR - sarcoplasmatic reticulum
- JSR - junctional SR - SR release compartment
- Vrel - SR release compartment volume 96.48 um³
- cri - calcium ion conc. in JSR
- icr - calcium release current from JSR
- krel - Max. release rate for icr 30 msec⁻¹

- NSR - network SR - SR uptake compartment
- Vup - SR uptake compartment volume 1109.52 um³
- cui - calcium ion conc. in NSR
- cupmax - Max. Ca²⁺ conc. in uptake compartment 15 mM
- Iupmax - Max. uptake Ca²⁺ current (Iup) by NSR 0.005 mM/ms
- Kup - [Ca²⁺]i half-saturation constant for Iup 0.00092 mM
- Trpn - Total troponin conc. in myoplasm 0.07 mM
- Kmtrpn - [Ca²⁺]i half-saturation constant for troponin 0.0005 mM
- Cmdn - Total calmodulin conc. in myoplasm 0.05 mM
- Kmcmdn - [Ca²⁺]i half-saturation constant for calmodulin 0.00238 mM
- Csqn - Total calsequestrin conc. in SR release compartment 10 mM
- Kmcsqn - [Ca²⁺]JSR (cri) half-saturation constant for calsequestrin 0.8 mM
- IpCamax - Max. Ca²⁺ pump current (IpCa) 0.00055 mA/cm²
- gCaL - Max ICaL conductance 0.248 mS/cm²
- gK1 - Max. IK1 conductance 0.1567 mS/cm²
- gKr - Max. IKr conductance 0.0588 mS/cm²
- gKs - Max. IKs conductance 0.258 mS/cm²
- gKur - Max. IKur conductance 0.13195 mS/cm²
- gnonspec - Max nonspecific Ication conductance 0 mS/cm²
- gnabar - Max INa conductance 15.6 mS/cm²
- gbNa - Max. Ibackground (Na) conductance 1.34e-3 mS/cm²
- gbCa - Max. Ibackground (Ca²⁺) conductance 2.26e-3 mS/cm²
- gto - Max. Ito conductance 0.33 mS/cm²
- Kneutral - electroneutral K⁺ - accumulation 3e-5 mA/cm²
- ImaxNax - Max Ca²⁺/Na⁺ exchange current (INaCa) 3.5 mA/cm²
- KnNacx - [Na⁺]o half-saturation constant for INaCa 87.5 mM
- KcNacx - [Ca²⁺]o half-saturation constant for INaCa 1.38 mM
- Naneutral - electroneutral Na⁺ - accumulation 3.5e-5 mA/cm²
- INaKmax - Max. Na⁺/K⁺-pump current (INaK) 0.00219 mA/cm²
- Kmnai - [Na⁺]i half-saturation constant for INaK 10 mM
- Kmko - [K⁺]o half-saturation constant for INaK 1.5 mM
- Tauct - scaling factor activation
- Tauinactf - scaling factor fast inactivation
- Tauinacts - scaling factor slow inactivation

---

2025-05-27 – Standardized to Markdown