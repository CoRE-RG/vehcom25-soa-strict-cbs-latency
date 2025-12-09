# vehcom25-soa-strict-cbs-latency
Simulation environment and tools for the Paper "Negotiating Strict Latency Limits for Dynamic Real-Time Services in Vehicular Time-Sensitive Networks." 
Contains exact versions of tools and simulation frameworks used to evaluate our Time-Sensitive Networking (TSN) integrations for strict latency limits in the automotive Service-Oriented Architecture (SOA). 

## References
If you use this project please add the following [reference](https://doi.org/10.1016/j.vehcom.2025.100985)
> Timo Salomon, Lisa Maile, Philipp Meyer, Franz Korf, Thomas C. Schmidt, "Negotiating Strict Latency Limits for Dynamic Real-Time Services in Vehicular Time-Sensitive Networks," Vehicular Communications, Elsevier, 2025. (in press)
```bibtex
@Article{smmks-nslld-25,
  author = {Timo Salomon and Lisa Maile and Philipp Meyer and Franz Korf and Thomas C. Schmidt},
  title  = {{Negotiating Strict Latency Limits for Dynamic Real-Time Services in Vehicular Time-Sensitive Networks}},
  journal = {Vehicular Communications},
  pages = {},
  volume = {},
  number = {},
  year = {2025},
  month = {},
  nope= "In Press",
  publisher = {Elsevier},
  doi   = {10.1016/j.vehcom.2025.100985},
}
```

If you use specific simulation models inside this project please refer to the projects readme to find the correct reference.

## Initialization and Setup

### Status
This project has been tested on Ubuntu 22.04 (+WSL) and Windows 11.

### Frameworks and tools

#### License
All frameworks are linked as git submodules and come with their own license (usually GPL or LGPL).

#### OMNeT++ Frameworks:
- [INET Framework](https://github.com/inet-framework/inet)
- [CoRE4INET](https://github.com/CoRE-RG/CoRE4INET)
- [FiCo4OMNeT](https://github.com/CoRE-RG/FiCo4OMNeT)
- [OpenFlow](https://github.com/CoRE-RG/OpenFlow)
- [SDN4CoRE](https://github.com/CoRE-RG/SDN4CoRE)
- [SOA4CoRE](https://github.com/CoRE-RG/SOA4CoRE)
- [SignalsAndGateway](https://github.com/CoRE-RG/SignalsAndGateway)

#### Worst-Case Latency Analysis:
- [TSNLatencyAnalysis](https://github.com/CoRE-RG/TSNLatencyAnalysis)
- [DYRECTsn](https://github.com/Kathess/DYRECTsn/tree/haw)

### Initialize Submodules
Initialize submodules from their respective repositories, recursive is required as the INET framework has multiple submodules itself.

```Bash
git submodule update --init --recursive
```

## Paper Scenarios
The scenarios CBS Max Latency study and the Car Net study are included in the frameworks. 
* OMNeT++ simulations are in ```SDN4CoRE/examples/papers/vehcom2025```.
* TSN standard formulas for latency analysis are in ```TSNLatencyAnalysis/scenarios```
* Network calculus tools are in ```DYRECTsn/scenarios```

Please check out the documentation in the referenced projects.

### OMNET++ Simulation 
1. Download OMNeT++ 6.0.2
    * [https://omnetpp.org/download](https://omnetpp.org/download)
2. Install OMNeT++
    * [https://doc.omnetpp.org/omnetpp/InstallGuide.pdf](https://doc.omnetpp.org/omnetpp/InstallGuide.pdf)
3. Start IDE
   * Select this repo as your workspace
4. Import projects into workspace
   * File -> Import... -> General -> Existing Projects into Workspace 
   * Click Browse and select this workspace as project as rood directory 
   * Select the projects CoRE4INET, FiCo4OMNeT, INET, OpenFlow, SDN4CoRE, SignalsAndGateways, and SOA4CoRE
   * Click Finish
6. Running a simulation
   * In the IDE go to SDN4CoRE -> examples -> papers -> vehcom2025 -> car -> omnetpp.ini
   * right click the omnetpp.ini and select run as 
   * This will also automatically build all dependencies
   * Click yes/ok if asked to use release build for all projects
   * If some frameworks state something about inconsistency just click okay and OMNeT will try to fix it
   * The OMNeT++ Qtenv should start and you can select a configuration, e.g., Study_WFullShaping_SI
7. Check the documentation of the frameworks and OMNeT++ for more details.
