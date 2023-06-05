## Introduction to Market Basket Analysis
  
### 1. Glossary

+ Frequent itemset mining: each of these itemsets will occur at least as frequently as a pre-established minimum support count, min sup. 
+ Association rules generation: these rules must satisfy minimum support and minimum confidence.
+ Association Rule Mining: primarily used when we want to identify an association between different items in a set and then find frequent patterns in a transactional database or relational database. An association rule implies that if an item A occurs, then item B also occurs with a certain probability. It is widely used to analyze retail basket or transaction data, and are intended to __identify strong rules__ discovered in transaction data using __measures of interestingness__, based on the concept of strong rules.

### 2. Business Use Cases

+ Design of catalogs
+ Cross-marketing
+ Customer shopping analysis
+ Recommender system

### 3. How to do MBA and how to use MBA?

- Disclose correlation relationships among huge amounts of transaction record
- Identify customer purchasing habits by finding associations between different items that customers place in their shopping baskets
- Develop marketing strategies by gaining insights into which items are frequently bought together by customers
- Execute selective marketing based on predictions, cross-selling, and planning their ledge space for optimal product placement

### 4. How dose MBA work?

- Collect transactional data: Collect data on customer transactions, such as the items purchased in each transaction, the time and date of the transaction, and any other relevant information.
- Preprocess the data: Clean and preprocess the data, removing any irrelevant information, handling missing values, and converting the data into a suitable format for analysis.
- Identify frequent item sets: Use association rules mining algorithms such as Apriori or FP-Growth to identify frequent item sets, sets of items often appearing together in a transaction.
- Calculate support and confidence: Calculate the support and confidence for each frequent itemset, which expresses the likelihood of one item being purchased given the purchase of another item.
- Generate association rules: Generate association rules based on the frequent itemsets and their corresponding support and confidence values. Association rules express the likelihood of one item being purchased given the purchase of another item.
- Interpret the results: Interpret the results of the market basket analysis, identifying which items are frequently purchased together, the strength of the association between items, and any other relevant insights into customer behavior and preferences.
- Take action: Use the insights from the market basket analysis to inform business decisions such as product recommendations, store layout optimization, and targeted marketing campaigns.
		
### 5. Types of MBA

- Association Rule Mining: It involves identifying frequent item sets and generating association rules that express the likelihood of one item being purchased with the purchase of another item. It is used to identify the relationships or associations between items in a transactional dataset.
- Sequence Analysis: This type of market basket analysis focuses on the order in which items are purchased in a transaction. It identifies frequent item sequences and generates sequential association rules describing the likelihood of one item sequence being followed by another.
- Cluster Analysis: This type of market basket analysis involves grouping similar items or transactions into clusters or segments based on their attributes. It helps to identify customer segments with similar purchasing behaviors, which can inform product recommendations and marketing strategies. WFM has built-in house basket-based segmentation.
	
### 6. Applications of MBA

- Retail: Identify frequently purchased product combinations and create promotions or cross-selling strategies.
- E-Commerce: Suggest complementary products to customers and improve customer shopping experience.
- Healthcare: understand which medications are often prescribed together and identify patterns in patient behavior or treatment outcomes.
- Product Placement: refer to placing the complimentary (pen and paper)and substitute goods (tea and coffee) together so that the customer addresses the goods and will buy both the goods together.
- Fraud Detection: identify purchase behavior that can associate with fraud on the basis of market basket analysis data that contain credit card usage.

### 7. Algorithms used in MBA
- Apriori Algorithm: a widely-used and well-known Association Rule algorithm and is a popular algorithm used in market basket analysis. It is also considered accurate and overtop AIS and SETM algorithms. It helps to find frequent itemsets in transactions and identifies association rules between these items. The limitation of the Apriori Algorithm is frequent itemset generation. It needs to scan the database many times, leading to increased time and reduced performance as a computationally costly step because of a large dataset. It uses the concepts of Confidence and Support. Apriori uses the result of antimontone property of support and makes the generation of frequent Item set faster by reducing the search space

BottleNecks of Apriori:
- Candidate generation can result in huge candidate sets
- Multiple Scans of Database: needs n+1 scans, n is the longest pattern
		
- FP Growth: known as Frequent Pattern Growth Algorithm. FP growth algorithm is a concept of representing the data in the form of an FP tree or Frequent Pattern. Hence FP Growth is a method of Mining Frequent Itemsets. This algorithm is an advancement to the Apriori Algorithm. There is no need for candidate generation to generate a frequent pattern. This frequent pattern tree structure maintains the association between the itemsets. A Frequent Pattern Tree is a tree structure that is made with the earlier itemsets of the data. The main purpose of the FP tree is to mine the most frequent patterns. Every node of the FP tree represents an item of that itemset. The root node represents the null value, whereas the lower nodes represent the itemsets of the data. The association of these nodes with the lower nodes, that is, between itemsets, is maintained while creating the tree. 
		
- ECLAT Algorithm: ECLAT algorithm stands for Equivalence Class Clustering and bottom-up Lattice Traversal. It is one of the popular methods of Association Rule mining. It is a more efficient and scalable version of the Apriori algorithm. While the Apriori algorithm works in a horizontal sense imitating the Breadth-First Search of a graph, the ECLAT algorithm works in a vertical manner just like the Depth-First Search of a graph. This vertical approach of the ECLAT algorithm makes it a faster algorithm than the Apriori algorithm.

Advantages over Apriori algorithm:
- Memory Requirements: Since the ECLAT algorithm uses a Depth-First Search approach, it uses less memory than Apriori algorithm.
- Speed: The ECLAT algorithm is typically faster than the Apriori algorithm.
- Number of Computations: The ECLAT algorithm does not involve the repeated scanning of the data to compute the individual support values.
		
### 8. Advantages of MBA
- Increases customer engagements
- Boosts sales and increases ROI
- Improve customer experience
- Optimizes marketing strategies and campaigns
- Helps in demographic data analysis
- Identifies customer behavior and pattern


