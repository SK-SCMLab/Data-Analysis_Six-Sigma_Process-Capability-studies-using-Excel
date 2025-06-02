# 🏊🏻 Process Capability Indices and interpretation in Manufacturing operations using Microsoft Excel
This repository represents a structured analysis of process capability study in a steel manufacturing workflow involving sequential machines for: 

1. **Casting**
2. **Grinding**
3. **Milling**
4. **Degreasing**
5. **Hot Rolling**
6. **Annealing**
7. **Pickling**
8. **Punching**
9. **Slitting**
10. **Cold Rolling**
11. **Finishing**
12. **Transport**

Each machine plays a crucial role in shaping, resizing, and finishing steel sheets to final product specifications. 

---

## 🤹🏻 Process Capability Studies
Process capability is how well the process is meeting customer (Cx) needs and expectations. It is a metric that reflects only the common cause of variation

| *Natural Process Limits* | *Specification limits* |
|--------------------------|------------------------|
|1. Indicators of process variations | 1. Target set for the process |
|2. Voice of the process | 2. Voice of the CX |
|3. Based on the past performance | 3. Based on the CX requirements |
|4. Real-time values | 4. Intended result |
|5. Derived from process data | 5. Defined by the CX |
|6. Consists of Upper Control Limit (UCL) & Lower Control Limit (LCL)| 6. Consists of Upper Specification Limit (USL) & Lower Specification Limit (LSL) |
If the control limits lie within the specification limits, the process could be considered capable. Conversely, if the specification limits lie within the control limits, the process will not meet CX requirements

---

## 💪🏼 Actions after comparing Natural process & Specification limits
| *Condition* | *Action*|
|-------------|---------|
|1. Process limits fall within the specification limit |1. No action required|
|2. Process spread and specification spread are approximately the same | 2. Adjust the process centering to bring the batch within specification limits |
|3. Process limits fall outside the specification limits | 3. Reduce variability by partitioning and targetting the largest offender |
Process capability is the actual variation in the process specification. To identify it, one needs to:
    - Plan for data collection
    - Collect data
    - Plot and analyze the data
The same data which is used for stability and normality analysis can also be used for capability

---

## 🙅🏼‍♂️ Process Capability Index - Cₚ
Capability is how well or how poorly our current process meets customer requirements or needs. Generally, Cₚ:
- Measures performance
- Is the indicator of the capability of a process
- Is the inherent variability of a characteristic of a process or product

                        Process Capability Index (Cₚ)  = (USL - LSL)/(6*σ)
The formula assumes the process is perfectly centered between upper and lower specification limits. It does not reflect how the process is actually performing in relation to the specification limits. 
Meanwhile, Process Capability (Cₚₖ) is developed to objectively measure the degree to which a process meets or does not meet Cx requirements.

                                    Cₚₖ = Min(Cₚₖₗ, Cₚₖᵤ)
                                    Cₚₖₗ = (Mean - LSL)/3σ
                                    Cₚₖᵤ = (USL - Mean)/3σ

*Conditions*
1. Cₚₖ < Cₚ => Mean is not centered between specificaiton limits
2. Cₚₖ = Cₚ => Mean is centered between specification limits
3. Cₚₖ > Cₚ => Mean exceeds specification limits
4. Cₚₖ < 1 => Action required
5. Cₚₖ > 1.33 => Acceptable
6. Cₚₖ >= 2.0 => World-class
---

## 🚵🏽 Case study 1: Steel Mnaufacturing Process Capability analysis
### ☄️ Objectives
- Monitor process performance for each machine individually
- Identify variation sources: common vs. special cause
- Evaluate process capability (Cₚ, Cₚₖ) for critical dimensions
- Use Excel-based tools for SPC (Statistical Process Control)

### 🔬 Interpretation
From the excel analysis: Cₚₖ = Cₚ = 0.33
The process is not capable in regards to true performance even though the mean looks centered
- The team must focus on reducing variation and work with operations to center the average output

In the sample data, it is assumed that 'Thickness' as a key factor in determining the quality of the produce

To select a characteristic for a process capability study, it should meet the following requirements:
- Should indicate a key factor in the quality of produce or process
- Should influence the value of the characteristic through process adjustments
- Operating conditions that affect the characteristic should be defined and controlled
- Determined by CX requirement or industry standards

---

## 🪄 Process Performance Indices
Process Performance Index verifies if the sample generated from the process is capable of meeting the customer requirements. It is only used when process control cannot be evaluated
- Process Performance (Pₚ)
- Process Performance Index (Pₚₖ)
- Process Capability Index (Pₚₘ/Cₚₘ)

|*Process Performance Index*|*Process Capability Index*|
|---------------------------|--------------------------|
| 1. Applies to a specific batch of output | 1. Applies to all batches of output |
| 2. Based on sample standard deviation | 2. Based on population standard deviation |
| 3. Long-term capability (Zₗₜ) - actual performance of the process over time | 3. Short-term capability (Zₛₜ) - potential performance of the the process in control at any point of time |

As the process variation reduces and/or as the process average reaches the target value (mean), the Cₚₘ or Pₚₘ index improves or becomes larger. The ideal value is 1.33 or greater. A process shift (p = Zₗₜ - Zₛₜ) reflects how well process is controlled usually by a factor of 1.5

- A typical process will shift by approximately 1.5 Std.Dev.
- Long term variation is more than the short term variation
- The difference between the short and long term shift is the Sigma shift
- A shift may be due to different people, raw material, wear and tear, time and so on
- The effects of process shift (p) become more negligible as the process capability increases. A six sigma process level of defects is not affected much by long-term variation

### 🏺 Conversion of long-term to short-term capability
|*Data collected*| *Short-term capability*| *Long-term capability*|
|----------------|------------------------|-----------------------|
|Short term data (Zₛₜ)| p| Add 1.5 |
|Long-term data (Zₗₜ) | subtract 1.5 | p| 

|*Short-term variation* | *Long-term variation*|
|-----------------------|----------------------|
| 1. Attributed to common cause variation | 1. Attributed to both common cause and special cause variation |
| 2. Variance inherent in the process | 2. -- |
| 3. Shows variance with subgroups | 3. Shows variance within & between subgroups |
| 4. Captures common cause variation | 4. Increases due to special causes |
| 5. Common causes are difficult to identify and correct and may require process redesign | 5. Special causes have to be identified and corrected for improvement |

---

## 🚪 Repository structure
CharacteristicValue_dataset.xlsx
- CharacteristicValueRule

---

## 🎏 Excel Functionalities used
1. Pivot Tables
2. AVERAGE() function
3. STDDEV.S() function
4. STDDEV.P() function
5. RANDBETWEEN() function
6. RAND() function
7. Histogram charts

*Customized formulas used*
- Pₚ: =LAMBDA(USL,LSL,SIGMA, (USL-LSL)/(6xSIGMA))
- Pₚₖ: =LAMBDA(USL,LSL,MEAN,SIGMA, MIN((USL-MEAN)/(3xSIGMA), (MEAN-LSL)/(3xSIGMA)))
- Cₚₖ: =LAMBDA(USL,LSL,Mean,SIGMA, MIN((USL-Mean)/(3xSIGMA), (Mean-LSL)/(3xSIGMA)))
- Cₚ: =LAMBDA(USL,LSL,SIGMA, (USL-LSL)/(6xSIGMA))

---

## 🧪 Requirements
- Microsoft Excel 2016 or later
- Basic understanding of Process variations in Manufacturing

*Quality is never an accident. It is always the result of intelligent effort* - John Ruskin
