

# Basics of energy system modeling

Energy system models generally think in terms of energy sources, energy sinks, energy converters and storages and the flows and connections between them. This implies a system boundary with an upstream energy reservoir, since energy cannot be created or lost. In the following we will go through all of these and learn more about when to use them.

## Sources

Sources deliver energy to the energy system within the model. Sources are often primary energy carriers, such as natural gas or solar radiation. If you have measured data of a production unit, such as the electricity production of a pv system, this can also be represented by a source. Basically anything that introduces energy into your system is considered a source.

![Representation of a source]()

## Sinks

Sinks are the opposite of sources. Sinks take energy from the energy system. Sinks are often some kind of energy demand outside the boundary of you energy system. Examples are the elctricity demand of a household or the heat demand of a industrial process.

![Representation of a snk]()

## Converters

Converters transform one type of energy in your system into another, usually with some kind of conversion rate. Examples for converters are pv-systems, heat pumps and chp units. The conversion rate can corresponds to the efficiency of an power plant or the factor between differnt measurement units.

![Representation of a converter plus example]()

## Storages

Storages stor energy of one type. During the storage duration storage losses can occur.Examples for storages are batteries and pumped hydro storages.

![Representation of a storages plus example]()

## Busses and Flows

The energy transfered from the output of one component to the input of another component is called flow. For example there exists a flow of electricity from the output of a pv system to the input of a heat pump. Flows of the same type can be connected via buses. Buses are often but not always some type of grid. 

![Representation of a bus plus example]()

In order to build your energy system model, you have to identify all sources, sinks, converters and storages of your system and connect them via flows and buses.

![Representation of the full energy system]()