# EconAgent: LLM-Empowered Economic Activity Simulation

## Project Overview

EconAgent is an innovative economic simulation framework that uses Large Language Models (LLMs) to simulate macroeconomic activities and agent behaviors. The project is built upon the Foundation framework from the AI Economist paper, extending it with LLM capabilities to create more realistic and dynamic economic simulations.

## Core Components

### 1. Foundation Framework (`ai_economist/foundation/`)

The foundation framework provides the base infrastructure for economic simulations with several key components:

#### Base Components (`foundation/base/`)
- `base_agent.py`: Defines the base agent class for economic actors
- `base_component.py`: Base class for economic components
- `base_env.py`: Environment setup and management
- `world.py`: Manages the simulation world state

#### Economic Components (`foundation/components/`)
- `simple_labor.py`: Handles labor market mechanics
- `continuous_double_auction.py`: Market simulation
- `simple_consumption.py`: Consumer behavior modeling
- `simple_saving.py`: Savings mechanism
- `redistribution.py`: Tax and wealth redistribution

#### Agents (`foundation/agents/`)
- `mobiles.py`: Implements mobile agents that can interact in the economic environment
- `planners.py`: Policy planning agents

### 2. Simulation System

#### Core Simulation (`simulate.py`)
The main simulation orchestrator that supports two types of policy models:
1. GPT-based model (`gpt_actions`)
   - Uses LLM for decision-making
   - Handles agent interactions
   - Maintains conversation history
   - Implements reflection mechanisms

2. Complex model (`complex_actions`)
   - Rule-based decision making
   - Parametric consumption and work choices
   - Deterministic economic behavior

#### Configuration (`config.yaml`)
Defines simulation parameters including:
- Agent policies
- Environment settings
- Component configurations
- Training parameters
- System resources

## Key Features

1. **Economic Agent Simulation**
   - Simulates individual economic agents with unique characteristics
   - Models labor markets, consumption, and savings
   - Implements realistic tax systems and redistribution

2. **LLM Integration**
   - Uses GPT-3.5-turbo for agent decision making
   - Maintains conversation history for context
   - Implements periodic agent reflection
   - Handles economic reasoning and decision explanation

3. **Economic Metrics**
   - Tracks GDP (nominal and real)
   - Monitors unemployment rates
   - Measures market dynamics
   - Records inflation metrics

## Usage

### Basic Simulation

To run a simulation with GPT-3.5:
```bash
python simulate.py --policy_model gpt --num_agents 100 --episode_length 240
```

To run with the complex model:
```bash
python simulate.py --policy_model complex --num_agents 100 --episode_length 240
```

### Configuration

The simulation can be customized through `config.yaml`, including:
- Number of agents
- Episode length
- Economic parameters
- Model configurations
- Component settings

## Implementation Details

### Agent Architecture
- Each agent has unique attributes (age, skill, location)
- Maintains state including wealth, income, and consumption
- Makes decisions about work and consumption
- Can learn and adapt through GPT-based reasoning

### Economic Environment
- Implements a complete economic cycle
- Includes labor markets with skill-based wages
- Features price dynamics and inflation
- Incorporates tax brackets and redistribution
- Tracks multiple economic indicators

### LLM Integration
- Uses prompts for economic decision-making
- Maintains conversation history for context
- Implements periodic reflection for learning
- Handles complex economic reasoning

## Data Collection and Analysis

The simulation saves various data points:
- Agent actions and observations
- Conversation histories (for GPT model)
- Economic metrics
- Environment states

Data is saved periodically (every 6 steps) and can be used for:
- Economic analysis
- Policy evaluation
- Agent behavior studies
- Market dynamics research

## Notes

- The simulation requires an OpenAI API key for GPT-based simulations
- Performance depends on the number of agents and episode length
- Regular checkpoints are saved for analysis and recovery
- The system supports both deterministic (complex) and LLM-based decision making