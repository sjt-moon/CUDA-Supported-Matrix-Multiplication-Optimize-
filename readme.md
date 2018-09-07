# CUDA-Supported Matrix Multiplication Optimization
## Objective
We experiment different ideas to hide latency for matrix multiplication. In this project, we designed several block-based models to get a better performance in FLOPs.

## Models
* Single Thread Single Output (STSO)
* Single Thread Multiple Outputs (STMO)
* Single Thread Multiple Vertical Blocks (STMVB)

## Performance
### STMO Model
![STMO Model](/pics/stmo-alg.png)
### STMVB Model
![STMVB Model](/pics/stmvb.png)
### Performance Plotting
![Performance](/pics/performance.png)

## Conclusion
Based on our experiments, we state that 
* shared memory is more efficient than global memory; 
* we could hide latency by adding workload for each of the threads, as we increase ILP and reduce the number of thread switches; 
* more active threads could help us improve occupancy, which would lead to a lower latency. It’s a trade-off between higher occupancy and more workload per thread.
