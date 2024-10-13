
Basically this paper is talking about using LoRA (as a rank=1 linear, lowrank * high rank)

> Upon the pre-trained parameter θ, our SPM is formulated as Mctar = {(vi sig , vi reg )|ctar }, each of which is inserted into the i-th layer,

[[One-dimensional Adapter.pdf#page=4&selection=215,0,248,10|One-dimensional Adapter, page 4]]

M_c_tar is actually the adapter of LORA inserted in every layer.



And then using classifier-free guidance, in which the subtraction of the noise of concepts are making sense to be seen a difference.

As a result, they can use this feature to curb unwanted concept:
>  Formally, given the target con- cept ctar , we pre-define a corresponding surrogate concept csur instructing the behaviour of the erased model when ctar is prompted. Then, to achieve ctar ← csur − η ∗ (ctar − csur ),

[[One-dimensional Adapter.pdf#page=4&selection=307,26,349,1|One-dimensional Adapter, page 4]]

Inspired by ECD, the parameter N here is aiming for controlling the magnitude of erasing:


> Our approach involves editing the pre-trained diffusion U-Net model weights to remove a specific style or concept. We aim to reduce the probability of generating an image x according to the likelihood that is described by the concept, scaled by a power factor η

[[Erasing Concepts from Diffusion Models.pdf#page=4&selection=143,0,150,0|Erasing Concepts from Diffusion Models, page 4]]

## Anchoring Loss 
Find a way to keep both consistency and influencing synonyms



Anchoring loss is a normal erasing loss yet used for synonyms as belows:
> Lanc = Ec∼D(·|ctar ) ∥ϵ(xt, ci, t|θ, Mctar ) − ϵ(xt, ci, t|θ)∥2 2  . (7) Combining the two components with balancing hyper- parameter λ, we can derive our total training loss as: L = Lera + λLanc. (8)

[[One-dimensional Adapter.pdf#page=5&selection=55,0,129,3|One-dimensional Adapter, page 5]]


**So basically they also aim not only for one word, but also many other words.**
That's why they do calculation of loss on multiple concepts.




- Finding global encoding tokens from CLIP and calculate product
- But different lengths of input results in the similarity is small
- So what they do is simply get the intersection of texts (mutual contents) and calculate the similarity

> To estimate the probability, we first compute the cosine distance in the CLIP [33] textual encod- ing space, referred to as sc f (p). However, the global-view representation could fail in capturing the correlation between the concept name and an elaborate user description. For in- stance, the score between Van Gogh and The swirling night sky above the village, in the style of Van Gogh is 0.46, but we expect the corresponding SPM to operate at its maximum capacity. To this end, we additionally introduce a unigram metric to identify the similarity at the token-level: sc t (p) = |T (c) ∩ T (p)| |T (c)| 

[[One-dimensional Adapter.pdf#page=5&selection=224,2,285,0|One-dimensional Adapter, page 5]]

> [!PDF|yellow] [[One-dimensional Adapter.pdf#page=4&selection=102,11,111,33&color=yellow|One-dimensional Adapter, p.4]]
> > s such, the original forward process y = W x is intervened by our SPM as follows:
> 
>



> [!PDF|red] [[One-dimensional Adapter.pdf#page=4&selection=481,5,483,16&color=red|One-dimensional Adapter, p.4]]
> >  in comparison with the large general semantic space that pre-trained models have obtained, hand-crafted prompts at the scale of 

