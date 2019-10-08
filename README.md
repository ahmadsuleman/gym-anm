**Status:** Active (under active development, breaking changes may occur).


# gym-anm

**gym-anm is an extension to the [OpenAI Gym](https://github.com/openai/gym) toolkit. It provides researchers 
with a tool to build and train reinforcement learning agents in environments 
modelling active network management tasks for electricity distribution 
networks.**
  <br>
  
[![Build Status](https://travis-ci.com/robinhenry/gym-anm.svg?token=y9jBzyzxgcYYHdKPqW9q&branch=master)](https://travis-ci.com/robinhenry/gym-anm)
  
Each `gym-anm` environment implements the same [general task](#general_task).
 
 This toolkit comes with a paper available at [ADD LINK], and 
 researchers should reference `gym-anm` with the BibTeX entry:
 ```bash
ADD BibTeX entry
```  

## Getting Started

These instructions will help you install `gym-anm` on your machine and get 
started.

### Prerequisites

A version of Python 3.5 or greater is required.

### Installing

You can install `gym-anm` with:
```
git clone https://github.com/robinhenry/gym-anm
cd gym-anm
pip install -e .
```

### Testing

We use the python [unittest](https://docs.python.org/3/library/unittest.html) 
framework for testing. To run a full coverage of `gym-anm`, first install 
[coverage](https://coverage.readthedocs.io/en/v4.5.x/install.html) with:
```
pip install coverage
``` 
and then, from the root project folder, run:
```
coverage run -m tests
coverage html
```

## General task<a name="general_task"></a>

Each environment built on top of `gym-anm` implements the same general active 
network management task (see 
[`gym_anm/envs/anm_env.py`](gym_anm/envs/anm_env.py)) in a specific 
electricity distribution network.
The agent's goal consists in minimizing total energy losses while satisfying 
operating network constraints. <br>

The action space is continuous (see [`gym.spaces.Box`](https://github.com/openai/gym/blob/master/gym/spaces/box.py)) 
and consists in setting, at each time step:
* the maximum real power output from each renewable energy generator (also 
known as the *curtailment value*),
* the real power injection from each distributed energy storage unit,
* the reactive power injection from each distributed energy storage unit.

For more details, see the original publication [ADD LINK].

## Environments

Specific `gym-anm` environments can differ in terms of:
* the topology and characteristics of the electricity distribution 
network,
* the observation space,
* the modelling of the stochastic processes present in the system.

For more information on building new environments, see [ADD LINK]. 

## Authors

* **Robin Henry** - *Initial work* - [add personal website url]

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
