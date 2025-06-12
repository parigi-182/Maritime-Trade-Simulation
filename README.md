# Maritime Trade Simulation

## Project Description

This is an Operating Systems Course Project from the University of Turin. The code represents a complex maritime trade simulation system where ships transport goods between ports, managing resources, synchronization, and inter-process communication.

This code is the result of combining a trio of first-time C programmers, an unquantifiable amount of caffeine, and an assignment with a not particularly high effort to reward ratio.

This project was build for an Italian audience, so I'll be translating/refactoring it whenever i have time to 

## System Overview

The simulation models:

- Multiple ports (each as a separate process)
- Multiple ships (each as a separate process)
- A central master process that coordinates everything

## Key components:

- Shared memory for data exchange
- Semaphores for synchronization
- Message queues for communication

## Simulation:

- Ships navigate between random ports if goods expiration dates allows it
- Goods have expiration dates and values
- Ports have limited docking capacity

## Resource Management:

- Shared memory for market data
- Semaphore-protected critical sections
- Message-based request system

The system is configured via config.txt which specifies parameters like:

- Number of ships, ports, and goods types
- Map dimensions
- Ship speeds and capacities
- Simulation duration (in days)

## How It Works

Master Process:
1. Initializes all shared resources
2. Spawns port and ship processes
3. Advances simulation days
4. Handles termination

Ship Processes:
1. Navigate between ports
2. Load/unload goods
3. Respond to port requests

Port Processes:
1. Initializes goods and resources
2. Just exists

## Output

The system generates several log files:
- out.txt - Main output
- log_dump.txt - Detailed status dumps
- log_mercato.txt - Market data
- log_navi.txt - Ship activities

# Technical Details
Uses Unix IPC mechanisms:

Shared memory (shmget, shmat)

Semaphores (semget, semop)

Message queues (msgget, msgsnd, msgrcv)

Implements complex synchronization to avoid race conditions

Handles signals for process management

## Notes

This project was developed as a learning exercise for:
- Process management
- Inter-process communication
- Synchronization techniques
- System programming in C

# Original repository:
https://github.com/Marco-Skiavone/ProgettoC