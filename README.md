# A simple Streamlit Data Analysis App for the NYC picks

Streamlit is more than just a way to make data apps, it’s also a community of creators that share their apps and ideas and help each other make their work better. Please come join us on the community forum. We love to hear your questions, ideas, and help you work through your bugs — stop by today!

## The first step is to create a new Python script. Let's call it uber_pickups.py.

Open uber_pickups.py in your favorite IDE or text editor, then add these lines:

    import streamlit as st
    import pandas as pd
    import numpy as np

Every application prides itself with a title. Add a title to the link:

    st.title('Uber pickups in NYC')

## Fetch some data
Now that you have an app, the next thing you'll need to do is fetch the Uber dataset for pickups and drop-offs in New York City.

Let's start by writing a function to load the data. Add this code to your script:

    DATE_COLUMN = 'date/time'
    DATA_URL = ('https://s3-us-west-2.amazonaws.com/'
            'streamlit-demo-data/uber-raw-data-sep14.csv.gz')

    def load_data(nrows):
        data = pd.read_csv(DATA_URL, nrows=nrows)
        lowercase = lambda x: str(x).lower()
        data.rename(lowercase, axis='columns', inplace=True)
        data[DATE_COLUMN] = pd.to_datetime(data[DATE_COLUMN])
        return data


## Share your app
After you’ve built a Streamlit app, it's time to share it! To show it off to the world you can use Streamlit Community Cloud to deploy, manage, and share your app for free.

It works in 3 simple steps:

1. **Put your app in a public GitHub repo** (and make sure it has a requirements.txt!)
2. **Sign into share.streamlit.io**
3. **Click 'Deploy an app' and then paste in your GitHub URL**

That's it! 🎈 You now have a publicly deployed app that you can share with the world. Click to learn more about how to use Streamlit Community Cloud.