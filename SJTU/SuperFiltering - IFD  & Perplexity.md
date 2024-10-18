## Objective
IFD = PPL(Y|X) / PPL(X)

The lower the IFD is, the easier the model would understand or follow the instructions and vice versa. **Thus, higher IFD indicates more difficulties to study, which is conducive to the performance.**

Train a rather smaller model (GPT2 - 124M) to measure IFD score.
![[Pasted image 20241018094207.png]]

By comparing to co-efficient of different scales of models, even though model has different reasoning ability, they identify IFD values in a similar way.

However, Perplexity varies acorss different models with different scales of models.