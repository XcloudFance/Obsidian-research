>  multiple-choice QA dataset with context passages in English that have an aver- age length of about 5,000 tokens, much longer than typical current models can process

[[Quality.pdf#page=1&selection=33,10,36,39|Quality, page 1]]

## Sources
- Project Gutenberg fic- tion storie
- Slate magazine articles from the Open American National Corpus
- Oepn Access Book
- Most of the Gutenberg texts are from the 1950s–1970s, while the other texts are mostly from the 1990s and after
- Including a HTML tag for paragraph breaks

## Question Writing
> We hire 22 writers—most with degrees or profes- sional experience in literature or teaching—from the freelancing platform Upwork and design a multi-part incentive structure to encourage diffi- cult yet answerable question

[[Quality.pdf#page=3&selection=90,0,94,28|Quality, page 3]]
![[Pasted image 20241013013316.png]]- Dataset Size:
    - Total questions: 6,737
    - HARD subset questions: 3,360
    - HARD subset percentage: 49.9% (about half)
- Data Source Distribution:
    - Gutenberg (mainly science fiction): 5,038 questions (74.8%)
    - Slate magazine articles: 1,156 questions (17.2%)
    - Other miscellaneous sources: 543 questions (8.0%)
- HARD Question Percentage by Source:
    - Gutenberg: 54.7%
    - Slate: 40.0%
    - Other miscellaneous: 26.2%
- Dataset Split:
    - Training set: 2,523 questions (37.4%)
    - Development set: 2,086 questions (31.0%)
    - Test set: 2,128 questions (31.6%)
- Question Type Distribution (top five):
    - 'What' questions: 42.2%
    - 'Why' questions: 24.6%
    - 'How' questions: 11.9%
    - 'Which' questions: 7.4%
    - 'Who' questions: 4.2%
- Article Length:
    - Average length: 5,159 tokens
    - Maximum length: 7,759 tokens
    - Minimum length: about 2,000 tokens (estimated from the chart)
- Question and Option Length:
    - Average question length: 12.5 tokens
    - Average option length: 11.2 tokens
- Human Performance:
    - Overall accuracy: 93.5%
    - HARD subset accuracy: 89.1%
- Data Collection Process:
    - Initially collected questions: 7,620
    - Finally retained questions: 6,737
    - Retention rate: 88.4%