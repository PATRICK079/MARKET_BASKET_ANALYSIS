# ASSOCIATION RULE LEARNING (ARL)

<img width="526" alt="Screen Shot 2024-10-09 at 00 28 22" src="https://github.com/user-attachments/assets/4e7d7e87-046a-4bb9-b38e-a020dd8e2c0a">

# Introduction

Market Basket Analysis is one of the key techniques used by large retailers to uncover associations between items. It works by looking for combinations of items that occur together frequently in transactions. To put it another way, it allows retailers to identify relationships between the items that people buy.

Association Rules are widely used to analyze retail basket or transaction data and are intended to identify strong rules discovered in transaction data using measures of interestingness, based on the concept of strong rules.

# Business problem

 Following the valuable insights and recommendations which I provided from my previous customer segmentation analysis-specifically regarding premium customers who are high spenders and high-income customers who are low spenders—the company is now looking to further optimize its sales strategy. the company aims to increase sales and enhance customer retention. To achieve this, They’ve planned to implement targeted promotional campaigns  and loyalty packages as I have recommended. 

Now, they  require expertise in analyzing their  historical sales data to identify associations between store items. By understanding their  item associations, they can optimize store layout and tailor loyalty programs to encourage additional purchases among high spenders. The goal is to leverage these insights to strategically arrange products and design personalized loyalty offerings that boost sales and strengthen customer loyalty.

KINDLY CHECK MY CUSTOMER SEGMENTATION ANALYSIS FOR BETTER UNDERSTANDING: https://github.com/PATRICK079/CUSTOMER_SEGMENTATION.git


# Problem Encountered

During the project, I encountered an issue where the column names in the dataset were inconsistent, with some being in uppercase, others in lowercase, and some containing spaces. This inconsistency caused errors when i fed the data to my model.

# Explanation of Change
To resolve this, i went back to my dataframe and critically check every row for irregularities. i began by standardizing the column names by converting them all to lowercase and replacing any spaces with underscores. This ensured uniformity and prevented further errors during the analysis.  below are the codes used for the correction

df.columns.str.lower().str.replace(' ', '_')

df['itemdescription'].astype('str').apply (lambda x: re.sub(r'\s+', ' ', x).strip())



#  Key Learnings from the Project


I gained a comprehensive understanding of the steps required to build a robust Apriori model for association rule mining. This included learning the key metrics—support, confidence, and lift—and understanding the intuition behind each:

● Support:  Indicates how frequently an itemset appears in the dataset.

● Confidence:  Measures the likelihood that an item is purchased given that another item is purchased.

● Lift:  Assesses the strength of a rule by comparing the confidence with the expected confidence under independence.

Additionally, I learned that before applying the Apriori algorithm, the dataset must be converted into a transaction list format. This is essential for the algorithm to identify frequent itemsets and generate rules. I also discovered that when a dataset does not include headers, it's necessary to set header=None when reading the data to avoid errors and ensure proper data loading.

# Model Implementation

●  Generating Frequent Itemsets: The first step involves identifying frequent itemsets from the transaction data using the Apriori algorithm. A minimum support threshold of 5% is set, meaning itemsets that appear in at least 5% of transactions are considered frequent. The use_colnames=True parameter ensures that the original column names are used in the output for better interpretability.

●  Generating Association Rules: Once the frequent itemsets are identified, the next step is to generate association rules. The association_rules function is used to find relationships between items, with confidence as the primary metric. A minimum confidence threshold of 4% is applied, meaning the rules generated must have at least a 4% probability of the consequent occurring given the antecedent.

●  Sorting the Rules by Lift: After generating the association rules, they are sorted by the lift metric in descending order. Lift measures the strength of the rule, indicating how much more likely the consequent is given the antecedent, compared to random chance. Sorting by lift helps prioritize the most impactful rules.



# Dataset Incitation 
 source: KAGGLE
 
 URL: www.kaggle.com/datasets/heeraldedhia/groceries-dataset




