 AHB-to-APB Bridge Verification Environment

 Overview

This project provides a comprehensive UVM-based environment for verifying an AHB-to-APB Bridge. The Bridge acts as the critical link between high-speed AHB Masters and lower-bandwidth APB Slaves. The goal of this environment is to ensure that data is transferred accurately across these domains while strictly adhering to both AHB and APB protocol standards.

 Key Features

* Dynamic Configuration: Supports a configurable number of AHB and APB agents, allowing you to scale the testbench as needed.
* Coordinated Sequences: Uses a virtual sequencer to manage complex, synchronized traffic between the AHB and APB interfaces.
* Protocol Checking: Features built-in SystemVerilog Assertions to verify burst continuity, address alignment, and signal stability.
* Data Integrity: An analysis scoreboard uses a predictive model to compare transactions, ensuring that what the AHB Master sends is exactly what the APB Slave receives.

 Project Organization

* AHB Agent: Contains the driver, monitor, and sequencer for the AHB Master interface.
* APB Agent: Handles the driver, monitor, and sequencer for the APB Slave side.
* Bridge RTL: Includes the hardware source code and interface definitions.
* Testbench: Houses the top-level environment, scoreboard, and virtual sequencer components.
* Tests: Contains the test library and the main UVM package.

 Getting Started

The project uses a standard Makefile for simulation with tools like Questasim or ModelSim.

To compile the entire environment, use:
-make sv_cmp

To run the default simulation test:
-make run_test

To generate and view a detailed coverage report:
-make report

 Verification Strategy

The environment is designed to test a wide variety of scenarios, including:

* Burst Transfers: Verifying Single, Incrementing, and Wrapping bursts of various lengths.
* Data Alignment: Testing 8-bit, 16-bit, and 32-bit transfers across different address boundaries.
* Reset and Stability: Ensuring the system recovers correctly from resets and maintains signal integrity during wait states.

 Planned Improvements

Future updates will focus on expanding the sequence library to include error-injection tests and further refining the functional coverage models to reach 100% coverage on all wrap-around boundary conditions.
