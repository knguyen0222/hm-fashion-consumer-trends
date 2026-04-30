# H&M Fashion Consumer Trends

## Overview
This project analyzes 31 million H&M transactions joined across 3 datasets 
to find hidden patterns in fast fashion consumer behavior. Using Malloy 
and DuckDB, I explored how age, membership status, color preferences, and 
seasonality drive purchasing behavior at one of the world's largest fast 
fashion retailers.

## The Problem
As someone who loves fashion and shops on a budget, I've always been curious 
about what actually drives consumer behavior in fast fashion. H&M markets 
itself as affordable, trendy, and increasingly sustainable, but does the 
data back that up? Who is their core customer, what do they actually buy, 
and does H&M's marketing actually influence their spending? These are 
questions that retailers, marketers, and investors deal with every day.

## How It Works
The analysis joins 3 datasets using Malloy and DuckDB:
- `articles.csv` — 105,000+ products with garment type, color, and department
- `customers.csv` — 1.4 million customers with age and membership info
- `transactions_train.csv` — 31 million purchase transactions with date, 
price, and sales channel

Note: Prices in this dataset are normalized by H&M and divided by 1000 
to protect actual pricing. To convert to real values, multiply all price 
figures by 1000 (e.g. 0.028 = $28.00).

## Key Findings

**Finding 1: H&M is fundamentally a women's brand**
Ladieswear generates $587K in revenue, which is more than triple Divided ($189K) 
and more than ten times Menswear ($48K). Despite marketing to everyone, 
H&M's business is built on female customers. Their menswear 
and children's lines, both in store and online, are not significant 
revenue drivers. If H&M were to refocus their entire brand strategy around 
their actual core customer, women, they would likely see even stronger 
returns. The data makes it clear that this is where H&M wins.

**Finding 2: Black is overwhelmingly the #1 color**
Black accounts for 11 million transactions, whcih is more than triple the second 
most popular color, white, at 3.4 million. Dark blue, beige, and light 
beige follow behind. H&M's core customer isn't buying trendy 
seasonal colors or bold prints, they're buying classic black basics in 
massive volumes year after year. This challenges the common assumption 
that fast fashion is driven by trend-chasing. The data says it's driven 
by affordable, timeless staples that customers buy repeatedly.

**Finding 3: Young customers shop almost exclusively online**
Every age group from 21-33 shops a great deal through channel 2 (online), 
with virtually no preference for in-store shopping. The shift to e-commerce 
is overwhelming, especially after 2019. H&M's core demographic has fully 
embraced digital shopping, which raises serious questions about the ROI 
of maintaining a large physical store footprint. Investing in a seamless 
digital experience, faster shipping, and easier returns would likely drive 
more value than opening new store locations.

**Finding 4: Summer is peak season — October is a surprise spike**
Transactions steadily increased from January through June, peaking in summer. 
October also spikes unexpectedly, likely due to the fall collection launches 
and back-to-school shopping among college student customers. This seasonal 
pattern suggests that H&M should prioritize inventory and marketing spend 
heading into summer, while also preparing for a secondary demand surge in 
early fall. Failing to do so could potentially mean missing revenue 
opportunities.

**Finding 5: Anonymous shoppers rival registered members**
Active members generate $660K in revenue, but 7.5 million anonymous 
transactions generate $208K, whcih is a significant portion of revenue from 
customers H&M knows nothing about. These mystery shoppers represent a 
major opportunity. If H&M could convert even a fraction of them into 
registered members through incentives like discounts or early access 
to new collections, they would gain valuable behavioral data on a massive 
and invisible customer segment.

**Finding 6: Opting out of marketing emails doesn't reduce spending**
Customers who opted out of fashion news emails generate $371K in revenue 
compared to $286K from regular subscribers. This is one of the most 
interesting findings in the entire dataset. Normally, more marketing 
touchpoints drive more spending, but the data tells a completely different 
story. Customers who said no to H&M's emails are actually spending more. 
This raises serious questions about whether H&M's email marketing strategy 
is effective, or whether it may even be dividing their highest-value customers.

**Finding 7: 25-27 year olds are H&M's most valuable customers**
The 25-27 age group dominates both transaction volume and revenue by a 
significant margin. With the black basics, online shopping, and Ladieswear 
findings, H&M's core customer profile becomes clear that a mid-20s woman 
would by affordable black essentials online. Every strategic decision H&M 
makes, from inventory planning to digital marketing to store design, should 
be filtered through whether it serves this specific customer.

**Finding 8: H&M's Conscious Exclusive sustainability line is virtually invisible**
Even with H&M heavily marketing their commitment to sustainability through 
their Conscious Exclusive line, it doesn't appear anywhere at the top 
selling departments. Market basics like Swimwear (2.5M transactions) 
and Trousers (1.7M transactions) very much dominate the sales data. 
Conscious Exclusive is not even on the top list. This is definitely the 
most interesting finding for H&M's long term brand strategy. It just shows
us that their sustainability isn't translating to actual purchasing 
behavior. Customers are still buying cheap, high volume basics regardless 
of H&M's green marketing. If H&M is serious about sustainability, the data 
suggests they need a different approach to making sustainable options 
accessible and appealing to their core customer, especially in a society where
fast fashion is deemed unethical.

## What I Learned
I was most surprised by two findings: opting out of marketing emails 
doesn't reduce spending, and that H&M's sustainability line is virtually 
invisible in the data. I expected engaged, subscribed customers to spend 
more, and I expected some evidence of H&M's sustainability push showing 
up in sales. Neither was true. If I did this again I would look more 
closely at whether the anonymous shopper group behaves differently by 
season, and whether sustainability interest has grown over the 2 year 
period in the dataset.

## Who Would Care
H&M's marketing and strategy teams would find the email marketing finding 
directly actionable — if opted-out customers spend just as much, the ROI 
on email campaigns needs to be reconsidered. Sustainability advocates and 
investors tracking H&M's ESG commitments would find the Conscious Exclusive 
finding concerning. Fashion analysts and retail strategists would use the 
age and seasonality data to inform inventory and campaign planning.

## How to Run
1. Clone this repository
2. Install the Malloy VS Code extension from [malloydata.dev](https://malloydata.dev)
3. Download the dataset files:
   - `articles.csv` and `customers.csv` are included in the `data/` folder
   - `transactions_train.csv` is too large for GitHub (3.7GB) — download it 
   directly from Kaggle and place it in the `data/` folder
   [[H&M Personalized Fashion Recommendations](https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations/data)].
   You will need to:
      1. Create a free Kaggle account
      2. Accept the H&M competition rules before downloading
      3. Download `transactions_train.csv` and place it in the `data/` folder

[H&M Personalized Fashion Recommendations](https://www.kaggle.com/competitions/h-and-m-personalized-fashion-recommendations/data)
4. Open the project folder in VS Code
5. Run `explore.malloy` for individual queries
6. Run `story.malloynb` for the full data story

## Dataset
H&M Personalized Fashion Recommendations — Kaggle
Provided by H&M Hennes & Mauritz GBC AB
31 million transactions, 1.4 million customers, 105,000+ products
