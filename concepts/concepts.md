# Concepts

## Modes of a trading system

Modes are logical groupings of trading systems that reflect their lifecycle. There are 3 of them (**development**, 
**ready** and **trading**) and a trading system can be in only one of them.


### Development mode

When a user creates a trading system it has this mode and it will remain in this mode during its development.
During development, any aspect of a trading system can be changed at will. After some time, when the user decides
that it is good enough, they can finalize the trading system, moving it into the **ready** mode.

*Finalization* is the process that closes the development, moving the trading system to the ready mode.


### Ready mode

A trading system is in **ready** mode when one of these conditions is true:
- Its development has finished and it is ready to be traded
- It has been traded in the past but its performance was not good and it needs a review

When in this mode, a trading system has limited editing capabilities. The only fields that can be modified are:
- Name
- Strategy type
- Overnight flag
- Tags

All other fields can be modified *only* if the trading system doesn't have any trade associated.

Trading systems in this mode are not considered by the trading engine so they don't generate trades.

### Trading mode

When a trading system is moved to the **trading** mode, the trading engine starts to generate trades for it.
In particular, the running flag (on/off) means:

- **Off** : The trading system is *not live* but it generates trades anyway. This is a particular status useful to
  monitor the system with real new data but acting like paper trading (orders are not sent to the broker). After 
  a few months of monitoring, if the performance is satisfactory, the trading system can be turned on to go live

- **On** : The trading system is considered *live* and orders are sent to the broker

A trading system in this mode cannot be modified and must be moved back to the *ready* mode if some changes are
required.


### Technical details

| Mode        | Conditions                                 |
|-------------|--------------------------------------------|
| Development | ts.finalized = false                       |
| Ready       | ts.finalized = true AND ts.trading = false |
| Trading     | ts.finalized = true AND ts.trading = true  |


