# Shor-s-Algorithm-Simulation-in-Python-and-Qiskit
The repo consists of sample Python code to simulate the step by step state vector evolution in Shor's algorithm and qiskit code to demonstrate Shor's algorithm run on IBM-Q for N=15,  = 7 and a=4 using 7 qubits and 5 qubit respectively. This code is part of a project work after completing the course "Introduction to Quantum Computing" - EE225, lectured by professor Hiu Yung Wong at San Jose State University. 

##1. Python code  
There are two Python programs 
- shor_matrix_mult.py
- shor_in_place_mult.py

### shor_matrix_mult.py
In this code, the quantum circuit is represented by its state vector (consisting of control register and target register). The evolution of the quantum circuit statevector will be performed by full matrix multiplication. The controlled U operator C-Ua shall be constructed as a full matrix and to be applied repeatedly to the state vector (equivalent to full Uf applied to the state vector). Similarly the IQFT shall be multiplied with identity matrix to convert to thw full matrix, before being applied to the state vector.

The benefit of this code is that is follow strictly the mathematical operations being applied to the state vector, so that it is easy for the learners to visuallize and track the progress step by step. The downside of it is that the matrix multiplication in Python runs slowly and requires large memory allocation. Therefore it is feasible for N=15. When increasing N=21, with n=5 qubit for the second register and 10 qubits for the first register, the state vector is 15 qubit, and the full matrix size 15^2 x 15^2 is huge, making the progam unable to run on personal computer.
This code is useful for N=15 only. The parameters N, a can be changed manually in the code as needed.

Plot example:
<img width="1392" height="479" alt="image" src="https://github.com/user-attachments/assets/84fac7bc-f9be-418c-82d0-dd092e6a4b89" />

### shor_in_place_mult.py
Optimized for speed by:
- Use 2-dimentional numpy array (state_2d variable) to efficiently manipulate the state vector
- Use the built-in ifft function (which is equivalent for IQFT) 

Plot example:
<img width="1390" height="495" alt="image" src="https://github.com/user-attachments/assets/32da0b6a-f917-485c-8c43-46435b51835e" />

Both programs use the shor_helper.py for printing and ploting the probability distribution.

##1. Qiskit code  
There are two Python programs 
- shor_matrix_mult.py
- shor_in_place_mult.py

### shor_matrix_mult.py
