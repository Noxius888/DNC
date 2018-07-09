### Differential Neural Computer
For the purpose of the Helix network topology and particularly the optimization of her connection rates, the 'Differential Neural Computer'(DNC) could be useful machine learning tool.
Basically it is a recurrent neural network with an  ***autoassociative* memory-matrix.***

Conventional recurrent networks working with senquential data, such as Long-Short-Term-Memory (LSTM) networks, can safe privious data in memory'-gates. However they are rather limited for the task of storing bigger and more complex data, which the neural network would take to learn from.

DNCs can store relevant findings in a memory matrix in form of weights and find assiciations with previously learnt concepts.

![DNC architecture](images/dnc.png)

The DNC possesses three different methods of *differentiable attention*, which are used by the read and write heads:
1.  **Content lookup**:  Key vector emitted by the controller is compared to the content od each location in memory according to similarity measure (**cosine similarity**)
2. **Temporal link matrix L**: Records transition between consecutively written locations in the N x N temporal link matrix L. L[i,j] is close to 1 if i was the next location written after j, and is close to 0 otherwise.
3. **Allocation of memory for writing**: The 'usage' of each location is represented as a number between 0 and 1. A weighting that picks out unused locations is delovered to the write head. The controller can reallocate memory that is no longer required. ***That means that a DNC can be trained on a task using one size of memory and can later be upgraded to a larger memory wihtout retraining!***

Future implementation will be based on DeepMind's template of the DNC https://github.com/deepmind/dnc.

The script in the Notebook is a rather simple implementation of a DNC for a better understanding using a feed-foward network as the controller. Later on, as described in the paper, the Controller can consist of different neural networks such as LSTMs and other RNNs.
