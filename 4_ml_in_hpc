# Workshop for machine learning in HPC

* next year will be a conference track
* paper submissions due march/april

## Keynote: Azalia Mirhoseini (Google Brain) 
### Addressing compute constraints
* trend towards more devices, bigger models, larger batch sizes
* mixture-of-experts is a new type of layer (billions of parms, but only millions of computations) - a new type of feed forward layer
* train a gating network, passes to sparse number of experts (experts are smaller models themselves)
* gating function: outputs a distribution over experts
* using MoE to concatenate regular layers for data parallelism
* results on WMT En-Fr dataset shows much larger models can train in less time
* https://github.com/tensorflow/tensor2tensor/blob/master/tensor2tensor/utils/expert_utils.py 
### Addressing memory contsraints
* problem is basically device placement (partitioning the model onto the devices)
* every new model currently requires a lot of knowlege & manual intervention
* propose using reinforcement learning to do it for them
* partioning works better than human expert
* the machine better handles the backprop loadbalancing, which is hard for the human to see, who primarily balances the feed foward graph
* even though data parallel was more computationally balanced per gpu, the RL-agent implicitly learned the cost of memcopy, and optimized for that
* https://github.com/tensorflow/tensorflow/blob/master/tensorflow/python/grappler
* ICLR18: A hierarchical model for device placement 
