# StressRefine Library Programmers guide

Conventional finite elements only require the local node numbers associated with an element. p-adaptive elements also require definitions of edges and faces to assure basis function continuity.

StressRefine creates these automatically, but it does require 3 setup calls:

 1. allocate space for elements. this is the number of conventional elements in your model that you want to convert to p-adaptive. If your model has 1,000,000 but you only need to convert 50,000, allocate space for 50,000
 2. 

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgyMTk3MjY3MCwtNzk4MjE2ODk1XX0=
-->