# mr_beast_clean_up

In this repo, my goal was to clean up the dataset to create a simple dashboard to put up on Kaggle ().

Used the publicly available dataset from Rob Mulla on Kaggle (https://www.kaggle.com/datasets/robikscube/mrbeast-youtube-stats-daily)

The dataset curated by Rob Mulla is much appreciated for this little project. The dataset, which was pulled 12/02/23, contains daily pulls from Mr. Beast's Youtube Channel.
> -Pulled by me 12/02/23
> -Dataset was first curated back in 12/24/21, and since there are daily pulls dating back that far, one can track daily numbers for certain videos.
> -Dataset contains multiple instances of the same video, totalling in 185,245 rows with only 666 unique 'id' values.
> -Dataset 'publishTime' and 'pull_date' are objects, need to convert to datetime before manipulation.

What I did:
> -as mentioned earlier, I used the to_datetime method to turn the 'publishTime' and 'pull_date' columns into a datetime format. **pd.to_datetime(beast_df['pull_date'])**
> -created a smaller dataset by using the idxmax method to keep the most recently pulled instance of a video by it's 'id'. **beast_df.groupby('id)['pull_date'].idxmax()**
> -dropped more than half of the columns that were irrelevant to what I needed
> -created the 'clean_beast.csv' which is available in this repo.
