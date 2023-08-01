# match-tables-with-fuzzy-matching

**Documentation**

**Objective:**
The objective of this project is to perform record linkage, also known as data matching, between two datasets, `dataset_A` and `dataset_B`, using fuzzy matching techniques. The goal is to identify potential matches between records based on various attributes such as company name, website, phone number, address, postcode, region, and country.

**Methodology:**
1. **Data Preprocessing:** The first step involves loading and preprocessing the datasets. The data preprocessing includes converting company names to lowercase, removing special characters, converting website addresses to a standard format, removing leading zeros from phone numbers, and converting postcodes to integers.

2. **Finding Common IDs:** Next, we find the common IDs between `dataset_A` and `dataset_B` based on three attributes: `id`, `website`, and `phone_number`. The common IDs represent the potential matches between the two datasets.

3. **Excluding Common IDs:** We exclude the common IDs from both datasets to get unmatched rows. These unmatched rows are further preprocessed by filling NaN values with empty strings. This will help to improve the running speed of fuzzy matching.

4. **Fuzzy Matching:** We perform fuzzy matching using the `fuzzymatcher` library on the unmatched rows. Fuzzy matching allows us to identify potential matches based on similarity scores between records.

5. **Filtering and Concatenation:** The fuzzy matching results are filtered based on the best_match_score threshold (in this case, >= -0.01 after trial and error). The filtered results are then concatenated with the common IDs to obtain the final set of matched records.

6. **Evaluation Metrics:**
   - **Precision:** Precision is the percentage of identified matches that are correct matches. It measures the accuracy of the matching process.
   - **Recall:** Recall is the percentage of actual matches that are listed in the results. It measures the completeness of the matching process.
   - **Performance:** Performance is evaluated based on the execution time of the implementation. A faster implementation is preferred for large datasets.

**Code Modularity and Readability:**
The code has been organized into separate functions, each serving a specific purpose. This ensures modularity and makes the code easier to understand and maintain. The function names are descriptive, indicating their respective tasks. Proper commenting is provided to explain the functionality of each function.

**Improvements:**
If I had more time, I would consider the following improvements to enhance the code and results:
1. **Parameter Tuning:** Experiment with different fuzzy matching parameters, such as the threshold for string similarity, to optimize the matching results.
2. **Handling Missing Values:** Implement advanced techniques to handle missing values and improve the quality of matches.
3. **Blocking Techniques:** Incorporate blocking techniques to reduce the number of comparisons and improve performance for large datasets.
4. **Matching Weights:** Assign different weights to different attributes during fuzzy matching to prioritize specific attributes for matching.
5. **Parallel Processing:** Explore parallel processing to accelerate the fuzzy matching process for large datasets.

**Conclusion:**
The implemented code successfully performs fuzzy matching between `dataset_A` and `dataset_B`, resulting in potential matches along with their similarity scores. The code demonstrates good modularity, readability, and accuracy in matching. However, there is always room for improvement, and the suggested enhancements can be explored to achieve even better matching results and performance.
