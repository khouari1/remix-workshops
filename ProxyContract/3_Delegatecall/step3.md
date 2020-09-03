The delegatecall is a special variant of a **message call**. In a delegatecall, the code at the target address is executed in the context of the calling contract so **msg.sender** and **msg.value** DO NOT change their values.

This means that a contract can dynamically load code from a different address at runtime. 

The storage, the current address, and balance still refer to the calling contract, only the code is taken from the called address. 

So when a **Proxy** delegates calls to the Logic contract, every storage modification will impact the storage of Logic contract.