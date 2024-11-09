# MPNN, Message Passing Neural Network
ICML 2017, Neural Message Passing for Quantum Chemistry, [https://doi.org/10.48550/arXiv.1704.01212](https://doi.org/10.48550/arXiv.1704.01212)

## Message Passing Phase
### message function
aggregate information from each node using neighbor and edge information

$$M(h_v,h_w,e_{vw})=A_{e_{vw}}h_w$$

$$m_v^{t+1}=\sum_{w\in N(v)}M_t(h_v^t,h_w^t,e_{vw})$$

### update function
update the node's next hidden state from the message

$$h_v^{t+1}=U_t(h_v^t,m_v^{t+1})$$

## Read Out Phase
repeat message passing phase as T time to obtain hidden state of each node and predict the final label of the graph

$$\hat{y}=R({h_v^T}|v \in G)$$
