# EM for Good

This repository contains Jupyter Notebook files designed to process traces for Electromagnetic Side Channel Analysis (EM-SCA). The analysis was conducted using a CW-Lite board with the default AES implementation from the ChipWhisperer library. An EM probe (1.25mm) from the Riscure kit (Keysight) was utilized, along with the CW-Husky capture board. Capturing was performed within the CW environment, enhanced by the SCAPEgoat library for improved trace project management and streamlined metric computations. An XYZ stage was controlled using the Trinamic Python library.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
  - [Capturing](#capturing)
  - [Post-Processing](#post-processing)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Features

- Computation of metrics and generation of heatmaps.
- Integration of SCAPEgoat methods, providing a one-click solution for trace analysis.

## Installation

1. **Install ChipWhisperer**:
   - Follow the installation instructions provided in the [ChipWhisperer documentation](INSERT LINK HERE).
   - *Note*: This step is only necessary if you plan to capture new traces.

2. **Clone the SCAPEgoat Library**:
   - Clone the SCAPEgoat library into the ChipWhisperer directory.
   - Set the appropriate path in the Jupyter Notebook for the imports.

3. **Download Traces**:
   - Download the required traces from the provided link (INSERT LINK HERE).

4. **Organize Notebooks and Traces**:
   - Place the EMSCA Jupyter Notebook within the downloaded traces directory, ensuring it is in the `CEMA` folder (acts as the parent directory).
   - Ensure the "functions" Jupyter Notebook is located alongside the EMSCA notebook.

5. **Verify Import Paths**:
   - Confirm that all import paths are correct in the EMSCA notebook to ensure seamless execution.

## Usage

The EMSCA process is divided into two main parts: capturing and post-processing.

### Capturing

Capturing requires access to the following equipment:

- CW Husky/Lite capture board
- CW Lite target board
- EM probe (compatible with SMA connections to the CW capture board)
- XYZ stage (Riscure/Keysight)

Each of these components has associated Python libraries for control. For storage and management, the SCAPEgoat library is utilized for file management and scope configuration during capture.

**Steps**:

1. **Initialization**:
   - Use helper scripts to compile the necessary C code.
   - Set up the scope and target using the `scope` class from the SCAPEgoat library.

2. **Experiment Management**:
   - Initialize a parent directory to store experiments.
   - Create a new experiment and initialize capture using the grid tracing function.

3. **Data Collection**:
   - Capture fixed and random traces for each grid location.
   - Store the captured data as datasets within the experiment.

### Post-Processing

For the provided traces, there are two experiments:

1. **Key and Plaintext Experiment**:
   - Contains keys and plaintexts (both random and fixed).
   - Used for reproducibility of experiments using the same set of keys and plaintexts.

2. **Trace Experiment**:
   - A 10x10 grid collection of traces.

**Metric Computation**:

- To compute metrics such as TVLA, SNR, and CEMA, call the `plot_heatmap` functions for each metric, providing the appropriate objects for both experiments.

## Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the Repository**:
   - Click on the "Fork" button at the top right of this page to create a copy of this repository under your GitHub account.

2. **Create a New Branch**:
   - Navigate to your forked repository.
   - Create a new branch for your feature or bug fix:
     ```bash
     git checkout -b feature/your-feature-name
     ```

3. **Make Your Changes**:
   - Implement your feature or fix the identified bug.
   - Ensure that your code follows the project's coding standards and passes all tests.

4. **Commit Your Changes**:
   - Add and commit your changes with a descriptive commit message:
     ```bash
     git add .
     git commit -m 'Add feature: your feature description'
     ```

5. **Push to Your Branch**:
   - Push your changes to your forked repository:
     ```bash
     git push origin feature/your-feature-name
     ```

6. **Submit a Pull Request**:
   - Navigate to the original repository.
   - Click on the "Pull Requests" tab.
   - Click on the "New Pull Request" button.
   - Select your branch from the "compare" dropdown.
   - Provide a clear and descriptive title and description for your pull request.
   - Click "Create Pull Request" to submit.

## License

This project is licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

## Contact

For any questions or to report a bug, please email me at [dmmehta2@wpi.edu](mailto:dmmehta2@wpi.edu).
