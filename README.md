# Grocery and Bank Queue Simulation

## Overview
This project simulates a **Bank Queue** and a **Grocery Queue** system, with configurable numbers of tellers/cashiers and queue lengths. Customers arrive, get assigned to the shortest queue, and are served based on the queue's availability. 

Two different queue models are simulated:
1. **Bank Queue Simulation**: This uses multiple tellers, each with a limited queue size. 
2. **Grocery Queue Simulation**: This involves multiple grocery queues, each managed by a cashier with a maximum queue length. If a grocery queue is full, a customer waits up to 10 seconds for an available spot.

## Key Features
- **Multithreaded Simulation**: Each customer queue (in both Bank and Grocery models) runs in parallel using threads, allowing multiple tellers/cashiers to serve customers concurrently.
- **Thread-Safe Queues**: The simulation employs locks to ensure thread-safe operations when multiple queues are accessed concurrently.
- **Customer Wait Mechanism (Grocery)**: In the Grocery simulation, customers can wait for a maximum of 10 seconds for an available spot in the queue, after which they leave if no space is available.

## Code Explanation

1. **QueueSimulator Class**: Manages both the Bank and Grocery simulations, handling customer arrival, queue management, and service time calculation.
    - **simulateBankQueue()**: Simulates a bank queue with configurable tellers and queue length.
    - **simulateGroceryQueues()**: Simulates multiple grocery queues with cashiers. Customers wait for space in a queue or leave if none becomes available within 10 seconds.
   
2. **Main Class**: Entry point to run the simulations.
    - Takes the simulation time in minutes as a command-line argument.
    - Simulates both BankQueue and GroceryQueues consecutively and prints the results for each.

## How to Run the Simulation

Visit the `src` directory to run the simulation:

1. **Compile the Code**:
   Make sure you have the Java Development Kit (JDK) installed on your machine.
   ```bash
   javac *.java
   ```

2. **Run the Simulation**:
   Run the compiled code by specifying the desired simulation time (in minutes) as a command-line argument.
   
   Example:
   ```bash
   java Main 60
   ```

   This will run both the **BankQueue** and **GroceryQueues** simulations for 60 minutes and output the results.

## Output Format
The program will print the results for both simulations, including:
- Total number of customers
- Total customers served
- Total customers left unserved (Grocery Queue specific)
- Average service time per customer

### Output for out simulation:
```
Simulating BankQueue with 3 tellers and max queue length of 5...
Bank Queue Simulation Results:
Total customers: 92
Total customers served: 60
Total customers left unserved: 27
Average service time: 180.38333333333333

Simulating GroceryQueues with 3 cashiers and max queue length of 2...
Grocery Queue Simulation Results:
Total customers: 88
Total customers served: 63
Total customers left unserved: 19
Average service time: 175.26984126984127
```

## Conclusion
This project demonstrates the use of multithreading to simulate real-world queue management scenarios (Bank and Grocery) with customizable parameters. The system efficiently manages multiple queues using thread-safe operations and provides detailed results for each simulation.