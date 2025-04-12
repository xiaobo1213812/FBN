# PF4SAFE: Problem Frames extension for Safety Analysis based on FBN Evaluation
## :blush: Declaration
This repository contains a summary overview of this paper, as well as the Conditional Probability Tables(CPT) and the content of questionnaire that we have proposed.

## 📄Overview
🔍Objective: The purpose of this study is to integrate safety factors into the Problem Frames (PF) framework to enhance the expression of safety requirements, enable both qualitative and quantitative analysis, and offer requirements analysts a broader and more systematic modeling perspective.

💡Method: In this paper, we propose an approach  based on FBN logical reasoning, eventually extended to problem diagram, to analyse safety requirements at a fine-grained level. Firstly, we interact with five LLMs to determine the priori and conditional probabilities via a triangular fuzzy function. We perform logical inference through FBN to derive the posteriori probabilities, which are transformed into system safety factors to determine the safety thresholds of each element in the system. Finally, the relevant fault nodes are mapped to the problem boundaries and the safety factors are visualised onto the problem diagram to extend the PF. We have analysed and verified a classical case of an airline's composite wing panels fault.

✒Contribution: 1) A prompt word template based on LLMs for analyzing safety requirements from faults is constructed, and role design is defined by prompt words to support requirements acquisition and fault assessment. 

2) The analysis of safety requirements can be synthesized into intuitive, systematic visualization charts with quantitative and qualitative analysis of the relationship between elements in the form of problem diagrams, thus increasing the granularity of safety requirements in the diagrams.

3) Method evaluation and case study are carried out, and the method evaluation proved the reliability of the PF4SAFE method, and the case study proved its feasibility.


## 📊The Conditional Probability Tables (CPT)


## 🗞The content of questionnaire



Extension of the safety factor to the problem diagram is obtained using LLMs based on FBN logical reasoning：

CPT：The conditional probability table of leaf nodes and intermediate nodes in the Bayesian network can be obtained from the mapping of fault tree logic gates, and the node association strengths are input into Niosy-OR model to obtain the CPT of each node.
