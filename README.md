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

---

## 🚵🏽 Case study: Steel Mnaufacturing Process Capability analysis
### ☄️ Objectives
- Monitor process performance for each machine individually
- Identify variation sources: common vs. special cause
- Evaluate process capability (Cₚ, Cₚₖ) for critical dimensions
- Use Excel-based tools for SPC (Statistical Process Control)

### 🛠 Machines & Process flow
| *Machine* | *Process stage* | *Key Parameters* |
|-----------|-----------------|------------------|
| Rolling | Flattening steel | Sheet thickness (mm) |
| Cutting | Dimensioning | Length & Width (mm) |
| Folding | Final shaping | Edge condition (degrees) |

Each stage is monitored for:
- **Cycle time**
- **Key output parameters**
- **Rework/Rejection rates**


