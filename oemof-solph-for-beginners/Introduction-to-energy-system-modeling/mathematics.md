# Mathematical background

For the mathematical basics of optimization models at large see ...

In the following you will find a abstract description of the typical formulation of a energy system optimization model. For a review of several energy system optimization frameworks and the implemented model respectively, see ...

For an detailed tutorial how this is implemented and can be used in oemof-solph see ... and the docu of oemof-solph.

## Time discretization

In order to implement an energy system optimization model the time horizion of the model has to be dicretized. For example a typical time horizon is one year, when looking at the operation of units to depict the seasonal changes within this year. To analyze the energy flows within this year the year is split in discrete time steps, often with a hourly resolution. But also quite a lot of other time resolutions are used as well. As a discussion of this time refer to the paper ... presented at the RetCon and the connected code tutorial in the oemof-solph docu.

## Objective function

The objective function represents the goal of the model. Typical objective functions in energy system models are to minimize costs or emissions. 

An objective function for the operation optimization of an energy system minimzes the sum of all operation related costs for all units and time steps.

$$min \sum_i^N \sum_t^T P_i(t)\cdot c_i(t)$$

For the investment planning optimization the objective function is enlarged by the costs for the capacity of units:

$$min \sum_i^N  (\sum_t^T P_i(t)\cdot c_i(t)) + P_{i,max}\cdot c_{i,inv}$$

## Parameters and variables

In energy system models one distingushes between model parameters and model variables. Parameters are exogenous values given to the model, such as costs, fixed demands or plant efficiencies. The value of variables is defined by the model during the optimization process. In energy system modeling typical variables are the power output of units at a particular point in time or the size of a power plant.

Parameters as well as varibles can be scalar values as well as values depending on the point of time (time series). Scalars have the same value for the optimization horizon, while time series values change with each time step of the model.

Variables are defined by some intial constraints regarding their nature. For example thei can be non-negative, integer or binary in nature. If defined in such a way, they can only take values within this type.

## Constraints

Constraints limit the values variables can take. They can be overall constraints for the whole optimization horizon or just apply to individual time steps. 

Typical optimization constraints in enregy system modeling are nodal balances, physical restrictions of power plants, such as efficiencies, and modeling choices such as emission limits.

Nodal balance constraints state, that all ingoing energy flows into a node have to be equal to all outgoing energy flows, i.e. energy can not be created or lost in a node:

$$\sum_i E_{in,i}+E_{out,i}=0$$

Example ...

Typical physical restrictions are:

The power output of unit has to be smaller than its size (max. power) forall time steps:
$$P(t)\le P_{max} \forall t \in T$$

The input and output of a converter is linked by the conversion factor (e.g. efficincy) of a unit:

$$P_{in}(t)\cdot \eta_{out}(t) = P_{out}(t)\cdot \eta_{in}(t) \forall t \in T$$

Another common constraint is the ramp rate of unit, i.e. how much the power output/input of a unit can change between one time step and the next:

$$P(t)\le P(t-1)\pm \Delta P $$

