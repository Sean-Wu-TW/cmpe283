### I re-did the assignment 2 bc I thought the previous version was wrong

### 1. I'm the only team member

### 2. Steps to finish this assignemt:
- Have a working assignment 2
- Modify the kvm_emulate_cpuid function inside cpuid.c to add a 0x4ffffffe block

#### Comment on the frequency of exits – does the number of exits increase at a stable rate?

The number of exits does not seems to increase at a stable rate. 

#### Or are there more exits performed during certain VM operations?

External Interrrupt, Interrupt Window , Control-register access, and IO seems to have a lot of exits.

#### Approximately how many exits does a full VM boot entail?

Roughly 500k.





