# PF4SAFE: Problem Frames extension for Safety Analysis based on FBN Evaluation
## :blush: Declaration
This repository contains a summary overview of this paper, as well as the Conditional Probability Tables(CPT) and the content of questionnaire that we have proposed.

## 📄Overview
🔍Objective: The purpose of this study is to integrate safety factors into the Problem Frames (PF) framework to enhance the expression of safety requirements, enable both qualitative and quantitative analysis, and offer requirements analysts a broader and more systematic modeling perspective.

💡Method: In this paper, we propose an approach  based on FBN logical reasoning, eventually extended to problem diagram, to analyse safety requirements at a fine-grained level. Firstly, we interact with five LLMs to determine the priori and conditional probabilities via a triangular fuzzy function. We perform logical inference through FBN to derive the posteriori probabilities, which are transformed into system safety factors to determine the safety thresholds of each element in the system. Finally, the relevant fault nodes are mapped to the problem boundaries and the safety factors are visualised onto the problem diagram to extend the PF. We have analysed and verified a classical case of an airline's composite wing panels fault.

✒Contribution:

1) A prompt word template based on LLMs for analyzing safety requirements from faults is constructed, and role design is defined by prompt words to support requirements acquisition and fault assessment. 

2) The analysis of safety requirements can be synthesized into intuitive, systematic visualization charts with quantitative and qualitative analysis of the relationship between elements in the form of problem diagrams, thus increasing the granularity of safety requirements in the diagrams.

3) Method evaluation and case study are carried out, and the method evaluation proved the reliability of the PF4SAFE method, and the case study proved its feasibility.

## 💭Data

### 📊The Conditional Probability Tables (CPT)

The conditional probability table(CPT) of leaf nodes and intermediate nodes in the Bayesian network can be obtained from the mapping of fault tree logic gates, and the node association strengths are input into Niosy-OR model to obtain the CPT of each node.

| **Cause**               | **Causes type**       | **Association strength（conditional probability）**                                                                 |
|-------------------------|-----------------------|-------------------------------------------------------------------------------------------------------------------|
| Manufacturing defect x1 | Material factors Y1   | P(y1 \| x1=0, x2=0) = 0.0000<br>P(y1 \| x1=0, x2=1) = 0.5400<br>P(y1 \| x1=1, x2=0) = 0.5950<br>P(y1 \| x1=1, x2=1) = 0.8137 |
| Material aging x2       | Material factors Y1   |                                                                                                                   |
| Design flaw x3          | Human factors Y2       | P(y2 \| x3=0, x4=0) = 0.0000<br>P(y2 \| x3=0, x4=1) = 0.4920<br>P(y2 \| x3=1, x4=0) = 0.4050<br>P(y2 \| x3=1, x4=1) = 0.6977 |
| Inadequate operational processes x4 | Human factors Y2      |                                                                                                                   |
| Climatic factor x5      | External environmental factors Y3 | P(y3 \| x5=0, x6=0) = 0.0000<br>P(y3 \| x5=0, x6=1) = 0.3650<br>P(y3 \| x5=1, x6=0) = 0.2800<br>P(y3 \| x5=1, x6=1) = 0.5428 |
| External shocks and accident x6 | External environmental factors Y3 |                                                                                                                   |
| Mechanical breakdown X7 | Equipment factors Y4  | P(y4 \| x7=0, x8=0, x9=0) = 0.0000<br>P(y4 \| x7=0, x8=0, x9=1) = 0.5950<br>P(y4 \| x7=0, x8=1, x9=0) = 0.6400<br>P(y4 \| x7=0, x8=1, x9=1) = 0.8542<br>P(y4 \| x7=1, x8=0, x9=0) = 0.6000<br>P(y4 \| x7=1, x8=0, x9=1) = 0.8380<br>P(y4 \| x7=1, x8=1, x9=0) = 0.8560<br>P(y4 \| x7=1, x8=1, x9=1) = 0.9417 |
| Gauge failure X8        | Equipment factors Y4  |                                                                                                                   |
| Hydraulic failure x9    | Equipment factors Y4  |                                                                                                                   |
| Improper maintenance x10 | Maintenance and inspection factors Y5 | P(y5 \| x10=0, x11=0) = 0.0000<br>P(y5 \| x10=0, x11=1) = 0.7300<br>P(y5 \| x10=1, x11=0) = 0.5000<br>P(y5 \| x10=1, x11=1) = 0.8650 |
| Improper inspection x11 | Maintenance and inspection factors Y5 |                                                                                                                   |
| Material factors Y1     | Failure of composite wing skin materials H | P(H \| Y1=0, Y2=0, Y3=0, Y4=0, Y5=0) = 0.0000<br>P(H \| Y1=0, Y2=0, Y3=0, Y4=0, Y5=1) = 0.7350<br>P(H \| Y1=0, Y2=0, Y3=0, Y4=1, Y5=1) = 0.6200<br>P(H \| Y1=0, Y2=0, Y3=0, Y4=1, Y5=1) = 0.8993<br>P(H \| Y1=0, Y2=0, Y3=1, Y4=0, Y5=0) = 0.6150<br>P(H \| Y1=0, Y2=0, Y3=1, Y4=0, Y5=1) = 0.8980<br>P(H \| Y1=0, Y2=0, Y3=1, Y4=1, Y5=0) = 0.8537<br>P(H \| Y1=0, Y2=0, Y3=1, Y4=1, Y5=1) = 0.9612<br>P(H \| Y1=0, Y2=1, Y3=0, Y4=0, Y5=0) = 0.6600<br>P(H \| Y1=0, Y2=1, Y3=0, Y4=0, x5=1) = 0.9099<br>P(H \| Y1=0, Y2=1, Y3=0, Y4=1, Y5=0) = 0.8708<br>P(H \| Y1=0, Y2=1, Y3=0, Y4=1, Y5=1) = 0.9658<br>P(H \| Y1=0, Y2=1, Y3=1, Y4=0, Y5=0) = 0.8691<br>P(H \| Y1=0, Y2=1, Y3=1, Y4=0, Y5=1) = 0.9653<br>P(H \| Y1=0, Y2=1, Y3=1, Y4=1, Y5=0) = 0.9503<br>P(H \| Y1=0, Y2=1, Y3=1, Y4=1, Y5=1) = 0.9868<br>P(H \| Y1=1, Y2=0, Y3=0, Y4=0, Y5=0) = 0.9000<br>P(H \| Y1=1, Y2=0, Y3=0, Y4=0, Y5=1) = 0.9735<br>P(H \| Y1=1, Y2=0, Y3=0, Y4=1, Y5=0) = 0.9620<br>P(H \| Y1=1, Y2=0, Y3=0, Y4=1, Y5=1) = 0.9899<br>P(H \| Y1=1, Y2=0, Y3=1, Y4=0, Y5=0) = 0.9615<br>P(H \| Y1=1, Y2=0, Y3=1, Y4=0, Y5=1) = 0.9898<br>P(H \| Y1=1, Y2=0, Y3=1, Y4=1, Y5=0) = 0.9854<br>P(H \| Y1=1, Y2=0, Y3=1, Y4=1, Y5=1) = 0.9961<br>P(H \| Y1=1, Y2=1, Y3=0, Y4=0, Y5=0) = 0.9660<br>P(H \| Y1=1, Y2=1, Y3=0, Y4=0, Y5=1) = 0.9910<br>P(H \| Y1=1, Y2=1, Y3=0, Y4=1, Y5=0) = 0.9871<br>P(H \| Y1=1, Y2=1, Y3=0, Y4=1, Y5=1) = 0.9966<br>P(H \| Y1=1, Y2=1, Y3=1, Y4=0, Y5=0) = 0.9869<br>P(H \| Y1=1, Y2=1, Y3=1, Y4=0, Y5=1) = 0.9965<br>P(H \| Y1=1, Y2=1, Y3=1, Y4=1, Y5=0) = 0.9950<br>P(H \| Y1=1, Y2=1, Y3=1, Y4=1, Y5=1) = 0.9987 |
| Human factors Y2        | Failure of composite wing skin materials H |                                                                                                                   |
| External environmental factors Y3 | Failure of composite wing skin materials H |                                                                                                                   |
| Equipment factors Y4    | Failure of composite wing skin materials H |                                                                                                                   |
| Maintenance and inspection factors H | Failure of composite wing skin materials H |                                                                                                                   |

### 🗞The content of questionnaire

1. Whether the diagram does have key elements?(1 to 5)
2. Whether the relationship between the components in the diagram is easy to understand?(1 to 5)
3. Whether the logical relationships in the diagram are clear?(1 to 5)
4. Whether the diagram involves safety requirements and constraints?(1 to 5)
5. Whether the safety information in the diagram is easy to read and understand?(1 to 5)
6. Whether the safety information in the diagram can directly provide you with the value of requirement prioritization?(1 to 5)

