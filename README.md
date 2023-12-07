# ****Sentiment and Political Orientation in Reddit Communities****

The link to the project: [https://necessary-alder-1fb.notion.site/Data-story-d448501e95e5411390e2bfaddbb1e916?pvs=4](https://www.notion.so/Data-story-d448501e95e5411390e2bfaddbb1e916?pvs=21)

## Abstract

In this project, we're investigating how the political stance of different Reddit communities relates to the emotions sentiment expressed in their comments. Our main goal is to see if subreddits with more extreme political views show stronger sentiment in their discussions. We think this is important because it can tell us a lot about how people express their political opinions online. By analyzing comments from various subreddits between 2019 and 2021, we aim to uncover patterns that show how political views is related with the way people communicate and express their feelings on Reddit.

## Research Questions

1. **Primary Research Question**:
    - *Correlation Between Sentiment and Political Orientation*: How does the sentiment expressed in comments across various subreddits correlate with the political stance?
        - Hypothesis: Community with more extreme political stance exhibit stronger sentiment.
2. **Secondary Questions**:
    - *~~Sentiment Analysis Across Subreddits*: What are the predominant sentiments expressed in comments across subreddits with different political orientations?~~
        - Tried different packages for emotion detection. Accuracy is low. Therefore abandon this.
    - *Comparison of News-Related and Regular Posts*: How do sentiments in news-related posts compare with sentiments in regular posts?
    - *Temporal Trends*: Are there any noticeable trends over time in the sentiments expressed in different politically-oriented subreddits, particularly in relation to major news events?

## Datasets

We employ a comprehensive collection of data from Reddit, comprising:

- **Text Comments**: A dataset encompassing the full spectrum of user comments, providing a rich source for sentiment analysis.
- **Text Submissions**: A dataset including submission titles and self-text, offering insights into the topics of discussion and the contextual sentiment within the subreddits.

The structure of our datasets is detailed as follows:

- Common attributes across both datasets include unique identifiers, scoring metrics, authorship information, subreddit categorization, and timestamp data.
- Comments-specific attributes feature parent submission identifiers and the comment body text.
- Submissions-specific attributes distinguish between text posts and linked content, as well as the domain of the linked content.

Additionally, we integrate external datasets

- For each subreddit's aggregated score, indicating its position on a political spectrum. Obtain the data from the paper `echo tunnels`. (Waller, I., Anderson, A. Quantifying social organization and political polarization in online platforms. *Nature* 600, 264–268 (2021). https://doi.org/10.1038/s41586-021-04167-x****)

## Methods

1. **Data Preparation and Cleaning**:
    - Checked for null values in each column to ensure data integrity.
    - Organized and cleaned the data to prepare for analysis.
2. **Sentiment Analysis**:
    - Conducted sentiment analysis on comments across various subreddits.
    - For each comment, defined a weighted sentiment as follows: number of upvotes multiplied by the sentiment score. If the number of upvotes was 0, used 0.01 instead to avoid null values.
    - Grouped data by subreddit to aggregate these weighted sentiment scores and count comments.
    - Utilized sentiment values to analyze the emotional tone of the comments.
3. **Data Normalization**:
    - Implemented MinMaxScaler to normalize average weighted sentiment scores.
4. **Political Orientation Analysis**:
    - Defined a threshold to categorize subreddits into left and right-leaning based on their political orientation.
    - Calculated correlation coefficients to understand the relationship between sentiment and political orientation.
    - Analyzed left and right-leaning subreddits separately for nuanced insights.
5. **Statistical Analysis**:
    - Calculated correlation and p-values for both left and right-leaning subreddits to validate findings.
    - Created a correlation matrix to visualize the relationship between different variables.
6. **Comparative Sentiment Analysis**:
    - Compared sentiments in different types of posts (news-related vs. regular posts).
    - Employed box plots and other visualization tools for a comparative analysis of sentiment types.
7. **Activity Analysis**:
    - Counted comments per subreddit and visualized the distribution using histograms.
    - Explored the relationship between political scores and sentiment scores through scatter plots and annotations.
8. **Temporal Analysis**:
    - Grouped data weekly and calculated average weighted sentiment scores.
    - Plotted temporal trends in sentiments, aligning them with major global and political events for contextual understanding.
9. **Visualization Techniques**:
    - Employed a range of visualization techniques including violin plots, boxplots, scatter plots, and heatmaps to present data in an accessible and informative manner.
    - Annotated plots with subreddit names for clearer interpretation.
10. **Major Events Correlation**:
    - Incorporated a dataset of major events to correlate sentiment trends with real-world happenings.
    - Visualized how these events impacted the sentiment in various subreddits.

This updated approach ensures a detailed and nuanced analysis of sentiment in political subreddits, accounting for the influence of user engagement (upvotes) on the perceived sentiment strength.

### **Limitations**

Our analysis recognizes several limitations that may impact the findings:

- **Partial Dataset**: The study is conducted on a subset of the entire Reddit dataset. Consequently, our results may not represent the sentiment and political orientation of all Reddit communities.
- **Political Orientation Bias**: Most subreddits in our dataset lean towards the left politically. This imbalance could introduce bias, as the sentiments from right-leaning or centrist communities are underrepresented.
- **Sentiment Analysis Tool Accuracy**: The tools used for sentiment analysis are not infallible and may not capture the subtleties of human emotion, leading to potential inaccuracies in sentiment scoring.
- **Political Score Complexity**: The process of scoring a subreddit's political orientation is inherently complex and may not fully encapsulate the diverse political views within the community.
