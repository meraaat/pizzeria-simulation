# Concurrent Pizzeria Simulation 🍕

## Overview

This Go project simulates a pizzeria's operations using concurrent programming techniques, demonstrating the power of goroutines, channels, and concurrent design patterns.

## Features

- 🔄 Concurrent pizza production
- 🎲 Randomized pizza-making process
- 📊 Real-time performance tracking
- 🌈 Colorful console output
- 🚦 Graceful shutdown mechanism

## Project Structure

### Key Components

- `Producer`: Manages pizza order production
- `pizzaOrder`: Represents individual pizza order details
- Concurrent goroutines for pizza making and processing

## Prerequisites

- Go 1.16+
- Dependencies:
  - `github.com/fatih/color` for colorful console output

## Installation

1. Clone the repository:
```bash
git clone https://github.com/meraaat/pizzeria-simulation.git
cd pizzeria-simulation
```

2. Install dependencies:
```bash
go mod init pizzeria
go get github.com/fatih/color
```

## Running the Simulation

```bash
go run main.go
```

## How It Works

### Pizza Production Process

1. Initialize random seed
2. Create a pizza producer
3. Start pizzeria goroutine
4. Consume and process pizza orders
5. Print daily performance statistics

### Concurrency Highlights

- Uses channels for communication between goroutines
- Implements producer-consumer pattern
- Demonstrates non-blocking channel operations
- Provides graceful shutdown mechanism

## Performance Metrics

The simulation tracks:
- Total pizzas made
- Pizzas failed
- Overall daily performance

### Daily Performance Categories

- **Awful Day**: >9 pizza failures
- **Not a Good Day**: 6-9 pizza failures
- **Okay Day**: 4-6 pizza failures
- **Pretty Good Day**: 2-4 pizza failures
- **Great Day**: <2 pizza failures

## Code Breakdown

### Randomization

Each pizza order has:
- Random production time (1-5 seconds)
- Random success probability
- Possible failure scenarios:
  - Running out of ingredients
  - Cook quitting
  - Successful pizza production

## Concurrency Patterns

- **Goroutines**: Background pizza production
- **Channels**: 
  - `data` channel for pizza orders
  - `quit` channel for graceful shutdown
- **Select Statement**: Non-blocking channel communication

## Error Handling

Implements advanced error handling with `chan chan error` pattern, allowing:
- Coordinated shutdown
- Error communication between goroutines

## Visualization

```
[Main Goroutine] ←→ [Pizzeria Goroutine]
        │               │
 Create Producer        │
        ├───────────────►
 Receive Orders         │
        ◄───────────────┤
 Process Orders         │
        ├───────────────►
```

## Customization

Modify these constants to adjust simulation:
- `NumberOfPizzas`: Total pizzas to produce
- Adjust randomization logic in `makePizza()` function

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit changes
4. Push to the branch
5. Create a Pull Request


## About

A fun project demonstrating Go's powerful concurrent programming capabilities through a pizzeria simulation.
