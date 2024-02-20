# lora  

[LORA](https://arxiv.org/abs/2106.09685) paper, code(./LoRA.py)

[LORA](https://wandb.ai/afterhoursbilly/lora/runs/) fine-training log
![alt_text](images/for_distinguished_gangster.png)

#### evals 
>Coming soon.

### Confusions about LoRA paper
> Heads up, I only trained GPT2-medium for implementation.

- I had a lot of confusion about the shapes of the A & B Matrix. It turns out you need to transpose them:  
    - `A = nn.Parameter(self.model.weight.new_zeros((r,k)).transpose(0,1))`
- I was also shocked to see that GPT2-medium didn't use `q,k,v` for the attention mechanism, but instead used Conv1D, which was a bit confusing to me at first.

You might see some of the confusion while looking at the training [code](./lora-training.py).



### Coming later, maybe...
QLORA - https://arxiv.org/abs/2305.14314e