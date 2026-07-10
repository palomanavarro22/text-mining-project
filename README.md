# Gendered Humor: A Text Mining Analysis of Stand-Up Comedy

![R](https://img.shields.io/badge/-R-276DC3?style=flat-square&logo=r&logoColor=white) ![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)

Sentiment, language, and topics across American stand-up comedy specials, comparing 5 female and 5 male comedians.

## Overview

This project uses text mining to explore whether female and male comedians differ in their language use in stand-up monologues. Three complementary methods are applied: TF-IDF to identify distinctive vocabulary, sentiment analysis to measure emotional register, and LDA topic modelling to uncover underlying themes.

## Key Findings

- **Vocabulary:** men's vocabulary is more marked by profanity, while women's is more marked by relational and emotional language (family, body)
- **Sentiment:** men's monologues are consistently more negative, though individual variation within each gender is considerable
- **Topics:** the LDA model (k=3) identified three clusters, Love/Body/Feelings, Home & Family, and My Story (first-person narrative). Women cluster around the first two, while men concentrate strongly in My Story
- **Overall:** results point to tendencies rather than a sharp gender-based division, individual comedic style matters as much as gender

## Methodology

1. **Data collection:** scraping of [Scraps From the Loft](https://scrapsfromtheloft.com/stand-up-comedy-scripts/) for monologues from 10 comedians (5 women, 5 men) with Netflix specials released 2019-2024
2. **Data cleaning:** removal of bracketed annotations (laughter, applause), tokenization, and a custom stopword list
3. **TF-IDF:** most frequent and most distinctive words per comedian and per gender
4. **Sentiment analysis:** Bing and NRC lexicons to score emotional tone and negative-word ratios
5. **Topic modelling:** LDA (k=3) to identify latent thematic clusters and their distribution by gender

## Repository Structure

```
text-mining-project/
├── text_mining_standup.qmd   # Full analysis (Quarto document)
├── data/
│   └── scripts_standup.csv   # Scraped stand-up comedy scripts
├── README.md
├── LICENSE
└── .gitignore
```

## Requirements

`R` (>= 4.2) with the following packages: `tidytext`, `tidyverse`, `tidyr`, `stringr`, `dplyr`, `wordcloud`, `topicmodels`, `textstem`, `ggplot2`, `reshape2`

```r
install.packages(c("tidytext", "tidyverse", "topicmodels", "textstem", "wordcloud", "reshape2"))
```

## How to Run

```bash
git clone https://github.com/palomanavarro22/text-mining-project.git
cd text-mining-project
```

Then open `text_mining_standup.qmd` in RStudio and render, or from the terminal:

```bash
quarto render text_mining_standup.qmd
```

## Limitations & Future Research

The corpus is small (10 comedians), which limits the reliability of the topic modelling results, and sentiment lexicons cannot detect irony, which may introduce some bias. Conclusions are specific to American English Netflix stand-up and are not meant to generalize to the genre as a whole. Future work could expand the corpus, incorporate irony-aware sentiment models, and compare across additional cultural contexts.

## Author

**Paloma Navarro and Gaspar Vigneaux**
MSc in Computational Social Science, UC3M
[LinkedIn](https://www.linkedin.com/in/paloma-navarro-3b7927280/)

## Citation

If you use this analysis, please cite:

```
Navarro, P. & Vigneaux, G. (2026). Gendered Humor: A Text Mining Analysis of Stand-Up Comedy.
GitHub repository: https://github.com/palomanavarro22/text-mining-project
```

## License

This project is licensed under the MIT License, see the [LICENSE](LICENSE) file for details.

---

*Final project for the Text Mining course, MSc in Computational Social Science, UC3M.*
