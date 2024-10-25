## Objective
IFD = PPL(Y|X) / PPL(X)
	
The lower the IFD is, the easier the model would understand or follow the instructions and vice versa. **Thus, higher IFD indicates more difficulties to study, which is conducive to the performance.**

## IFD - From Cherry LLM
![[Pasted image 20241018095742.png]]

![[Pasted image 20241018095806.png]]








Train a rather smaller model (GPT2 - 124M) to measure IFD score.
![[Pasted image 20241018094207.png]]

By comparing to co-efficient of different scales of models, even though model has different reasoning ability, they identify IFD values in a similar way.

However, Perplexity varies acorss different models with different scales of models.i

## Training
- For the given **instruction-tuning** dataset, the GPT-2 model is directly used to calculate the IFD score of each sample. 
- Then the top k-percent samples with the highest IFD scores under 1 are selected for faster instruction tuning.

![[Pasted image 20241018094650.png]]


## Ablation Study
- Proving that IFD filtering strategy less varies amongst different model weights.
- Traditional algorithms to select data are limited in performance.
![[Pasted image 20241018094713.png]]
