## Welcome to GitHub Pages


In May 2018, the Supreme Court voted to get rid of the Amateur Sports Protection act of 1992 (Hyperlink), and to allow the state to make the decision whether or not to allow sports gambling. Since then, more than 2 dozen states (hyperlink) have decided to legalize it. Although many of them only allow in-person betting, there has been traction in online betting. This is where I found interest in this topic, as many major players in the gambling industry have decided to develop their own platforms for online sports betting. Major players including DraftKings, MGM Resorts, Caesars Entertainment, Barstool (Penn National Gaming) and FanDuel (Flutter Entertainment). 

Having access to equities data with the R package TidyQuant (hyperlink), I wanted to analyze each of these major stocks -- specifically the trading volume of each stock, compare and create a forecast of what the volume will look like in two weeks.In my analysis I conducted EDA, identifying seasonality and trends with Decomposition (Utilizing the fpp3 package (hyperlink)), and wrote a function that identifies the best fitting model for each of the individual stocks. The best fitting models were ARIMA (Autoregressive Integrated Moving Average) and ETS (Exponential Smoothing) for individual stocks. When comparing the stocks, DraftKings and MGM Resorts had the highest forecasted trade volume, while FanDuel and CZR Entertainment had the lowest trading volume.


practicing my git fetch
Adjustments

You can use the [editor on GitHub](https://github.com/MatthewStoneMBA/Sports-Gambling-Equities-Analysis/edit/main/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for


```{r}
library(tidyverse)
library(lubridate)
library(tidyquant)
library(fpp3)
library(wesanderson)
library(distributional)
library(rmdformats)
# Creating Color palette
cPal <- c("#009E73", "black", "red", "#0072B2", "#D55E00")


```


## DraftKings
### Ticker - DKNG
```{r, cache=TRUE}
# Pull DraftKings Data
draftK <- c("DKNG") %>% 
  tq_get(., from = "2015-01-01") %>%
  as_tsibble(., 
             index = date) 
# DraftKings Adjusted close price
draftK %>% autoplot(adjusted) + 
  labs(
    title = "DraftKings Adjusted Price", 
    y = "Adjusted Stock Price ($)", 
    x = "Year (1D)", 
    subtitle = "    ") +  theme_minimal()
# DraftKings Volume 
draftK %>% 
  autoplot(volume) + 
  labs(
    title = "DraftKings Volume", 
    y = "Trade Volume", 
    x = "Year (1D)", 
    subtitle = "   ") + theme_minimal()
# Most recent day
draftK %>% 
  tail(1)
```


```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/MatthewStoneMBA/Sports-Gambling-Equities-Analysis/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
