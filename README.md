# Prosept_hackathon

Building a service for semi-automatic product markup.

## Objective
Development of a solution that automates the process of matching the customer's goods with the posted goods of dealers.

The programming language used is python.

## Solution Description

The main hypothesis is the assumption that the product names are sufficient to obtain a match with reasonable accuracy. To carry out the validation of this hypothesis, the cosine_similarity method is chosen and applied to the vectors of names obtained using TfidfVectorizer() and SentenceTransformer('LaBSE'). The column vectors df_dealerprice.product_name and df_product.name are matched. The other features are not used, as the hypothesis testing resulted in a positive result.

## Results

The chosen basic hypothesis was confirmed, the proposed methods TfidfVectorizer and SentenceTransformer('LaBSE') applied to the column vectors df_dealerprice.product_name and df_product.name gave excellent results. However, there are still flaws in the used names from the customer and dealers. Some deficiencies, such as missing spaces between words, can be eliminated by correcting data errors. However, it is not possible to correct such deficiencies as incorrect description of the product from the dealer. 

Data preprocessing was completed in the course of the project. A method of comparing top n customer names with dealer names using cosine_similarity ranking was developed. I obtained excellent code execution speed and excellent metrics. In the final version the choice fell on TfidfVectorizer, which produces 86% of correct names in the top 5 and executes in less than 1 second, because it showed fast performance and due to the simplicity of libraries represents the easiest and most reliable option.
