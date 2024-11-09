# Set2Set Pooling

1. compute current query vector $$q _t$$ by updating the previous query vector $$q_{t-1}^*$$ through the LSTM.

$$q_t=LSTM(q_{t-1}^*)$$

2. compute interaction score between node $$i$$ and query

$$e_{i,t}=f(m_i,q_t)$$

3. compute attention value using softmax about node $$i$$

$$a_{i,t}=\frac{exp(e_{i,t})}{\sum_j exp(e_{j,t})}$$

4. find graph vector at current time $$t$$

$$r_t=\sum_i a_{i,t}m_i$$

5. combine query vector and graph vector at current time, used as input of next LSTM

$$q_t^*=[q_t, r_t]$$
