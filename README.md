# Sequoia3

To reproduce the main results

    cd tests
    bash run.sh
    
A command should be in the format like

    python testbed.py --model  JackFram/llama-68m   --target meta-llama/Llama-2-7b-hf  \
    --T 0.6 --P 1.0  --start 0 --end 200 --M 384 \
    --growmap ./A100_growmaps/68m_7b/growmaps/A100-CNN-68m-7b-stochastic.pt \
    --Mode greedy --dataset cnn

`testbed.py` is for stochastic decoding. `testbed_greedy.py` is for greedy decoding. `test_specinfer.py` is for specinfer sampling. `test_greedyS.py` is for Top-k/greedy sampling. `test_accept.py` is for preparing the accepting rate vector.

`--model` specifies the draft and `--target` spefifies the target. Currently, only Llama models are supported (including Llama2, Sheared-LLaMA, Vicuna and TinyLlama).

`--T` specifies the temperature and `--P` spefifies the top-p for generation. 

`--dataset` should be in `cnn, openwebtext, c4`.  `--start` and `--end` decides how many examples will be evaluated. `--seed` is for adjusting random seeds. To precisely reproduce the results, seed is set to be 17 by default.

`--growmap` specifies the tree structure. We have prepared some growmaps in `A100_growmaps` and `L40_growmaps`. To generate your own growmaps, you can run

    python tree_search.py










