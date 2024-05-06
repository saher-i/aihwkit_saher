 # IBM Analog Hardware Acceleration Kit Unit Cell Extension

This repository is the forked version of IBM's AIHW Kit (https://github.com/IBM/aihwkit.git)

# What is the project about?

Analog in-memory compute (AIMC) represents a promising alternative architectural approach to enhancing throughput and energy efficiency of matrix-vector multiplications (MVM), which are often the dominant operations within deep neural network applications. In this project, we will be adding hardware functionality to IBM’s open-source AI Hardware Toolkit by extending the unit cell, the most fundamental circuit within our AIMC design, from two analog memory devices to four. In this design, neural network weights are typically represented using differential pairs of conductances W = G+ - G-. We will extend this functionality to W = F (G+ - G-) + g+ - g-, where four conductances now define the weight using a flexible scale factor F that can modulate the relative contributions and enable more accurate representations of broader weight distributions. Using multiple conductances also provides redundancy, which can improve network resilience (accuracy) in the presence of faulty or high variability devices.

# Outline of the Code Repository

- The repository consists of a 7 directories in total, my focus was on the modification of the 'src' directory.
- For implementation of my project, I made changes in the inference, simulator and nn directory within the src directory.
- In order to test my changes, I had to run the examples present in the examples directory.

In order to access and run the code on your local machine, please go through the following steps:

Step 1:
```
git clone https://github.com/saher-i/aihwkit_saher.git
```
Step 2:
```
pip3 install aihwkit
```
Step 3:
```
pip3 install -r requirements-examples.txt
```
Step 4:
```
cd examples
```
Step 5:
```
python3 01_simple_layer.py

In general:
python3 'example_name.py'
```
Step 6:
```
Changes made by me can be seen in the src directory:

cd src
```
# Results and Observations

The essential implementations encompassed the
modification of gamma_vec and the introduction
of the DualPairConductanceConverter class. In ad-
dition to these changes, adjustments were applied
to various segments of the code to address issues
related to programming errors, manage read noise,
and accommodate drift for four conductances, as
opposed to the previous configuration for two con-
ductances. These alterations collectively ensure the
robustness and efficacy of our methodology in han-
dling multiple conductance pairs while mitigating
potential sources of error and enhancing overall
performance

