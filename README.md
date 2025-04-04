# Neuroplastic Expansion v.s. FoG
<p>
  <img src="https://github.com/nothingbutbut/ICML-NE_compare/blob/main/HalfCheetah-v4-performance.png" alt="HalfCheetah-v4" style="width:48%; float:left; margin-right:2%;">
  <img src="https://github.com/nothingbutbut/ICML-NE_compare/blob/main/humanoid-walk-performance.png" alt="humanoid-walk" style="width:48%; float:left; margin-left:2%;">
</p>
<p style="clear:both;">
  <img src="https://github.com/nothingbutbut/ICML-NE_compare/blob/main/dog-run-performance.png" alt="dog-run" style="width:48%; float:left; margin-right:2%;">
  <img src="https://github.com/nothingbutbut/ICML-NE_compare/blob/main/dog-walk-performance.png" alt="dog-walk" style="width:48%; float:left; margin-left:2%;">
</p>
<p style="clear:both; font-size:18px; margin-top:20px;">
  In this experiment, we compare Neuroplastic Expansion (NE) with FoG. **NE(Small)** is the original NE algorithm implementation provided by the authors(https://github.com/torressliu/neuroplastic-expansion/tree/main), with normal MLP networks and update to data ratio of 1. **NE(Large)** is the same implementation but with a larger model size (depth=4, ~10M params) and update to data ratio of 2. As NE will sparsify connections, we use a SAC algorithm backnone and a smaller model size to minimize the total number of parameters for FoG to ensure a fair comparison. For **FoG**, we start with MLPs(which is different from our default setting in paper) and end with a maximal depth of 2 and maximal number of parameters of ~5M. Also, we use an update to data ratio of 2 for FoG. No resets or other tricks are used for both NE and FoG. The results are shown in the figures above. We can see that while NE(Large) outperforms NE(Small), it still lags behind FoG. Which demonstrates that FoG has better capability of scaling up the model size and sample efficiency. Besides, NE may be more suitable for easier tasks and smaller update to data ratio, while FoG is more suitable for harder tasks and larger update to data ratio. Such a difference in design choices may also contribute to the performance gap.
</p>
