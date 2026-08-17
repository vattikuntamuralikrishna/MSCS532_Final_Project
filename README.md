                                          HPC Data Structure Optimization
                                          
**Overview**
This project demonstrates a simple data structure optimization for High-Performance Computing (HPC). It compares two different ways of storing and processing particle data:
•	Array of Structures (AoS) – uses Python objects to store each particle.
•	Structure of Arrays (SoA) – uses NumPy arrays to store particle attributes separately.
The goal is to see how changing the data structure can affect the performance of a numerical workload.

**How it works:**
The program creates 1,000,000 particles and updates their positions for 10 timesteps.
For the AoS approach, each particle is stored as a Python object containing its position, velocity, and mass.
For the SoA approach, the particle properties are stored in separate NumPy arrays. The position updates are then performed using NumPy vectorized operations.
The program uses time.perf_counter() to measure the execution time of both approaches.

**Requirements**
Python 3.x
NumPy

**How to Run**
Clone the repository and run the Final_Project1.ipynb

**Results**
The test was performed using:
•	Particles: 1,000,000
•	Timesteps: 10
•	Time step value: 0.01

**The results from my test were:**
Implementation	Execution Time
AoS Python Objects	2.4206 seconds
SoA NumPy Arrays	0.0292 seconds

The optimized SoA implementation achieved an **82.78× speedup** compared with the AoS implementation.

**Conclusion**
The experiment shows that the way data is organized can have a significant effect on performance. The SoA approach performed much faster for this particle-update workload because it uses separate NumPy arrays and vectorized operations instead of processing individual Python objects in a loop.
The exact execution time may be different on other computers because hardware and system conditions can affect performance.
