# A/B-Testing-Marketing-Promtions

This case study is used to implement analysis on which promotion was the most effective in marketing?

## Scenario:

_A fast food chain plans to add a new item to its menu. However, they are still undecided between three possible marketing campaigns for promoting the new product. In order to determine which promotion has the greatest effect on sales, the new item is introduced at locations in several randomly selected markets. A different promotion is used at each location, and the weekly sales of the new item are recorded for the first four weeks._

**Dataset Description**: 

**MarketId**: an inhouse tag used to describe market types, we won't be using it

**AgeOfStores**: Age of store in years (1–28). The mean age of a store is 8.5 years.

**LocationID**: Unique identifier for store location. Each location is identified by a number. The total number of stores is 137.

**Promotion**: One of three promotions that were tested (1, 2, 3). We don’t really know the specifics of each promotion.

**Sales in Thousands**: Sales amount for a specific LocationID, Promotion and week. The mean amount of sales are 53.5 thousand dollars.

**Market size**: there are three types of market size: small, medium and large.

**Week**: One of four weeks when the promotions were run (1–4).

Key insights from the analysis -

- Sales distribution acrsoss 3 different promotions

    ![7](https://github.com/gagan-gets-data/A-B-Testing-Marketing-Promotions/assets/134737002/8c03dfdc-fe72-4c21-ac0c-f47fbdd7472d)

- Breakdowns of market sizes across different promotions
![8](https://github.com/gagan-gets-data/A-B-Testing-Marketing-Promotions/assets/134737002/c94b5659-abf3-4b38-90dd-4e1e47266d19)
![9](https://github.com/gagan-gets-data/A-B-Testing-Marketing-Promotions/assets/134737002/8a6d4f9e-41fd-46c3-8c10-9b68d417d124)

- Overall distribution of store ages
![10](https://github.com/gagan-gets-data/A-B-Testing-Marketing-Promotions/assets/134737002/97851465-9ee7-43e1-9dc5-099a9b7307e0)

- This table makes it easy to understand the overall store age distribution from our summary stats.

![11](https://github.com/gagan-gets-data/A-B-Testing-Marketing-Promotions/assets/134737002/7c40033f-6500-42d5-b8c7-9475ce2a667b)

**All test groups have similar age profiles and the average store ages is ~8 to 9 years old for theese 3 groups. The majority of the stores are 10–12 years old or even younger.**

**This indicates that our sample groups are well controlled and the A/B testing results will be meaningful and trustworthy.**

# Performing A/B Testing

![12](https://github.com/gagan-gets-data/A-B-Testing-Marketing-Promotions/assets/134737002/8061a3c9-7519-4688-9850-ff0720ea9b4f)

## T-Value v/s P-Value

The T-value measures the degree of difference relative to the variation in our data groups. **Large t-values indicate a higher degree of difference between the groups.**

P-value measures the probability that the results would occur by random chance. **The smaller the p-value is, the more statistically significant difference there will be between the two groups.**

## Running t-Test between Promotion 1 and 2

![14](https://github.com/gagan-gets-data/A-B-Testing-Marketing-Promotions/assets/134737002/82aee7ac-aad1-4f88-8916-970578039afd)

Our P-Value is close to 0 which suggests that there is good evidence to REJECT the Null Hypothesis. Meaning the there is a statistical difference between the two groups. Our threshold rejectings the Null is usually less than 0.05.

Our t-test shows that the marketing performances for these two groups are significantly different and that promotion group 1 outperforms promotion group 2.

## Running t-Test between Promotion 1 and 3

![13](https://github.com/gagan-gets-data/A-B-Testing-Marketing-Promotions/assets/134737002/a32a9415-93b1-4b82-9693-2370d0478c59)

We note that the average sales from promotion group 1 (58.1) is higher than those from promotion group 2 (55.36).
But, running a t-test between these two groups, gives us a T-value of 1.556 and a P-value of 0.121.
The computed p-value is a lot higher than 0.05, past the threshold for statistical significance.
