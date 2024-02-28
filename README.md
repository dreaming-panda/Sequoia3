# Sequoia3

To reproduce the main results
    cd tests
    bash run.sh
    
A command should be in the format like
    python testbed.py --model  JackFram/llama-68m   --target meta-llama/Llama-2-7b-hf  \
    --T 0.6 --P 1.0  --start 0 --end 200 --M 384 \
    --growmap /home/zhuoming/workspace/Sequoia3/A100_growmaps/68m_7b/growmaps/ \ A100-C4-68m-7b-stochastic.pt  --Mode greedy

`testbed.py` 




