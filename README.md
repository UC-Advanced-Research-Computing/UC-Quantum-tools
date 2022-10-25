# UCQ_tools
See the project on pypi for the download at:
https://pypi.org/project/U-Cincy-quantum-tools/

## Bugs
If you encounter a bug please make an issue in the "issues" tab above. This is a maintained repo and we will respond.

## Contributing
Anyone who wants to contribute to the code, please do. Download the code, modify it, and create a pull request.

## Available Functions
- Functions from `UC_Quantum_Lab.commands`
    - `state`
        - **Description** Displays a vector in vscode if using the UC_Quantum_Lab vscode extension. And no matter what it will return the state vector as a list.
            - **NOTE**: this function can be multiple times (whenever you can this function the statevector of the circuit up to the call will be created).
        - **inputs**:
            - `circuit:QuantumCircuit`: a qiskit quantum circuit **with no measurements in it**.
            - `show:boolean` (optional): a boolean indicating if you want to display the statevector in the UC_Quantum_Lab vscode extension.
        - **returns**:
            - `statevector:list`: the statevector of the circuit in little endian format (this is how qiskit orders bits) in list form. You do not have to use this return (just do not assign it to a variable).
    - `display`
        - **Description** Displays a circuit diagram in vscode if using the UC_Quantum_Lab vscode extension. If you are not using the vscode extension, then if you provide input *path* then the circuit diagram will be saved to that path and if you do *not* input *path* then a matplotlib figure will pop up.
            - **NOTE**: this function can be multiple times and it will just generate more images (whenever you can this function a diagram of the circuit up to the call will be created).
        - **inputs**:
            - `circuit:QuantumCircuit`: a qiskit quantum circuit.
            - `path:string` (optional): a string path that you want to save the figure to.
            - **NOTE**: if you are not using this function with the UC_Quantum_Lab vscode extension and you do not provide the path then a matplotlib figure will pop up.
        - **returns**: (nothing)
    - `counts`
        - **Description** Displays a histogram in vscode if using the UC_Quantum_Lab vscode extension. If you are not using the vscode extension, then if you provide input *path* then the histogram will be saved to that path and if you do *not* input *path* then a matplotlib figure will pop up.
            - **NOTE**: this function can be multiple times and it will just generate more images (and simulate the circuit at every call).
        - **inputs**:
            - `circuit:QuantumCircuit`: a qiskit quantum circuit **that must have measurements in it**.
            - `backend:simulator` (optional): the simulator to execute the circuit on, default is IBM's qasm simulator. 
            - `path:string` (optional): a string path that you want to save the figure to.
            - **NOTE**: if you are not using this function with the UC_Quantum_Lab vscode extension and you do not provide the path then a matplotlib figure will pop up.
        - **returns**:
            - `counts:dictionary`: the results of the simulation of the circuit as a dictionay where the keys are the binary strings and the values of the keys are the number of the times the binary string is the output of the circuit out of 1024. You do not have to use this return (just do not assign it to a variable).

- Functions from `UC_Quantum_Lab.layout`
    - `invert`
        - **Description** This only works with the vscode extension UC_Quantum_Lab. Inverts the tiling of the extension's UI vertically and horizontally from default.
        - **inputs** (nothing)
        - **returns** (nothing)
    - `horizontal_invert`
        - **Description** This only works with the vscode extension UC_Quantum_Lab. Inverts the tiling of the extension's UI horizontally from default.
        - **inputs** (nothing)
        - **returns** (nothing)
    - `vertical_invert`
        - **Description** This only works with the vscode extension UC_Quantum_Lab. Inverts the tiling of the extension's UI vertically from default.
        - **inputs** (nothing)
        - **returns** (nothing)

