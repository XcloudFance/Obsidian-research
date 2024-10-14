> [!PDF|yellow] [[Second Order Information.pdf#page=1&selection=173,57,182,1&color=yellow|Second Order Information, p.1]]
> >  1) compromise the generalizability in exchange for better performance on specific data/models [10 , 11 ]

## Challenges
- generalizability
-  should not avoid introducing overhead but also demonstrate robustness of effectiveness
> [!PDF|note] [[Second Order Information.pdf#page=2&selection=12,37,17,36&color=note|Second Order Information, p.2]]
>  certified removal [13 ] can largely remove the influence of deleted data points and derive an upper bound of residual information.

> [!PDF|important] [[Second Order Information.pdf#page=2&selection=19,34,21,7&color=important|Second Order Information, p.2]]
> second-order information in retaining the knowledge of remaining data and stabilizing the unlearning process

- model cannot be applied by certified removal directly since non-convexity

> [!PDF|red] [[Second Order Information.pdf#page=2&selection=79,51,87,14&color=red|Second Order Information, p.2]]
> > , namely Fisher Removal and Fisher Forgetting, which are both derived from Newton update.

Newton update is used for getting the roots of non-linear function.
- first derivative (**gradient**), and second derivative (**Hessian** matrix) at the current point.
![[Pasted image 20241015015243.png]]

It means the **mutual information of Interest of D-** and **output of original model** should be smaller than **the expectation of D-** between **original** model with **unlearned** model


