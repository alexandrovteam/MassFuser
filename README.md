# MassFuser: a workflow for combining MS1 and MS2 data from replicate LC-MS runs

The idea behind MassFuser is to take advantage of the high resolution acquisition mode of modern mass spectrometers, and at the same time overcome its inherent limitation of longer instrument duty cycles. The principal use case of MassFuser is combining the data from replicate LC-MS runs, one of which is acquired in high resolution mode, giving accurate m/z values in MS1 scans, whereas the other one is processed with lower resolution mode and data independent MS/MS acquisition enabled. Thus, both LC-MS runs contain complementary information, which gets merged by MassFuser allowing for downstream analysis with any software tools accepting regular LC-MS data.

The workflow is being developed by [Alexandrov Team](http://www.embl.de/research/units/scb/alexandrov/index.html) at EMBL Heidelberg ([contact information](http://www.embl.de/research/units/scb/alexandrov/contact/index.html)) in collaboration with Louis-Félix Nothias ([Pieter Dorrestein Lab, UCSD](http://dorresteinlab.ucsd.edu/Dorrestein_Lab/Welcome.html)).

Developer: Ivan Protsyuk

Principal investigator: Theodore Alexandrov

## Description

MassFuser operates within KNIME environment and contains two input nodes for two types of LC-MS runs: high-resolution MS1 data and low-resolution MS1,2 data respectively. Paired LC-MS runs should appear in the same order in the input nodes. The merging procedure is performed by the `Fuse MS1,2 data` node that starts with retention time alignment for every pair of LC-MS runs, then orders scans from different files accordingly and saves the resulting scan sequence to an output file in mzML format. `Fuse MS1,2 data` has two parameters that can be changed in its configuration dialog depending on the data: `m/z tolerance (ppm)` and `RT tolerance (s)`. They specify maximum allowed deviation of m/z and RT values for the same ions within a pair of LC-MS runs.

## System requirements

Only 64-bit operating systems are supported; MS Windows, Linux or Apple macOS. A workstation should provide a level of performance sufficient to run KNIME Analytics plaform and Python interpreter.

Note that the workflow makes use of multiple CPU cores to parallelize the merging procedure.

## Installation

In order to run the workflow, you will need to have KNIME Analytics platform and Python 2.7 interpreter installed.

Find the installation instructions in the [Optimus worfklow repository](https://github.com/MolecularCartography/Optimus#installation), which also runs within KNIME environment.

## License

The content of this project is licensed under the Apache 2.0 licence, see the LICENSE file in this repository.
