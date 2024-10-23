[[One-shot Learning.pdf]]

![[Pasted image 20241023123840.png]]

## Motivation
> [!PDF|yellow] [[One-shot Learning.pdf#page=3&selection=107,9,110,16&color=yellow|One-shot Learning, p.3]]
> > These methods encompass the application of heuristic rules, expert analysis, and iterative adjustments to the data guided by feedback on model performance

> [!PDF|red] [[One-shot Learning.pdf#page=3&selection=125,6,127,35&color=red|One-shot Learning, p.3]]
> > As the extent of improvement becomes more conspicuous, the instruction gravitates towards classification as “golden instruction”.
## Methodology

### Zero-shot Score



![[Pasted image 20241023124131.png]]
- ![[Pasted image 20241023160353.png]]
简单来说就是用1-shot的能力和0-shot的能力的差别去看0-shot过滤后的能力距离目标还有多远

这个思路感觉和super filtering很像，用conditional的perplexity和non conditional的比例去计算

## Evaluation
- MT-bench > [!PDF|red] [[One-shot Learning.pdf#page=6&selection=298,29,301,34&color=red|One-shot Learning, p.6]]
> >  which evaluates instruction-following proficiency across eight categories: writing, roleplay, extraction, reasoning, math, coding, STEM, and humanities




![[Pasted image 20241023163431.png]]