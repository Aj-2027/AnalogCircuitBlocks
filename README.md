# Performance Analysis of Analog Circuit Blocks  
**By:** Akriti Jain (ABV IIITM, Gwalior)

---

## Introduction
- **Objective:** Present simulation results of analog design blocks.  
- **Tools Used:** Cadence Virtuoso, GPDK 180nm.  
- **Metrics Evaluated:** Gain, CMRR, Slew Rate, ICMR, Phase Margin, Gain Margin, Power Consumption, Bandwidth, Unit Gain Frequency, Total Harmonic Distortion (THD), Noise, Offset Voltage Error.  
- **Analysis Types:** AC, DC, Transient, Monte-Carlo, PVT, Noise, Stability, XF.  

---

## 1. One-Stage Op-Amp
Single differential pair with active load (PMOS/NMOS current mirror). Bias current is supplied via a tail current source, typically implemented using a current mirror. This configuration is faster than a two-stage op-amp due to fewer internal nodes. All transistors are biased in saturation.
  
---

## 2. Two-Stage Op-Amp
First stage: Differential amplifier with active load for high gain and CMRR.  
Second stage: Common-source amplifier to boost gain and provide output drive.  
Miller capacitor is used for compensation between the stages. Bias currents are set by current mirrors. Overall gain is the product of both stages, making it suitable for high-gain applications.  

---

## 3. Telescopic Op-Amp
Single-stage op-amp with stacked transistors for high gain. Consumes low power and provides high speed but has limited output swing. Suitable for high-speed, low-power applications. Requires precise biasing to maintain all MOSFETs in saturation.  

---

## 4. Folded Cascode Op-Amp
Uses a folded structure to route current from the input differential pair to the cascode load. Improves output swing compared to telescopic op-amp while providing high gain. More complex biasing is required due to folding. All transistors are biased in saturation.  

---

## 5. Biased Folded Cascode Op-Amp
Enhances gain and allows higher output swing. Uses current mirrors for bias generation and load to ensure current matching. Cascoding and high output impedance contribute to high gain.  

---

## 6. Bandgap Reference (BGR)
Generates a temperature-independent reference voltage (~1.2 V) by combining PTAT and CTAT voltages. Bias-independent and process-stable, suitable for ADCs, LDOs, and op-amps.  

---

## Conclusion
-Studied different op-amp topologies and their trade-offs in gain, swing, and power.

-Simulated all designs using DC, AC, transient, noise, and Monte Carlo analysis.

-Telescopic gives high speed; folded cascode offers better swing.

-Designed a BGR circuit with a stable, temperature-independent output.

-Gained practical understanding of analog circuit behavior using Cadence.

## References
-Design of Analog CMOS Integrated Circuits - Behzad Razavi

-Fundamentals of Microelectonics - Behzad Razavi

-A Sub-5 ppm/°C Bandgap Voltage Reference with Dual Source-Sink Current Compensation By Hanru Yang, Tianrui Lyu, Xiao Huang, 
Jianping Guo (Sun Yat-sen University, Guangzhou, China)

