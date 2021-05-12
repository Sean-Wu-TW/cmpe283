### 1. For each member in your team, provide 1 paragraph detailing what parts of the lab that member
implemented / researched. (You may skip this question if you are doing the lab by yourself).
Ans: Myself.

### 2. Include a sample of your print of exit count output from dmesg from “with ept” and “without ept”.
Ans: I am not able to run the kvm, couldn't find `modules` folder in my `lib` folder.

### 3. What did you learn from the count of exits? Was the count what you expected? If not, why not?
Ans: 

### 4. What changed between the two runs (ept vs no-ept)?
Ans: Turning off opt forces shadow paging. In shadow paging, page fault exit gets turned on, the VMM 
allocates an empty page table to store the GVA -> HPA. The VMM will look at what address is failing then redo it again.
Thus, the number of exits will increase.
