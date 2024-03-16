# YouTube Data Harvesting and Warehousing using SQL and Streamlit
Harvest the YouTube data via YouTube Data API v3, storing in MongoDB for flexibility and then in MySQL for structured querying. Streamlit app enables scraping channel data, migrating to MySQL, and querying for insights, providing a comprehensive solution for YouTube data management and analysis.


the provided Python code demonstrates how to scrape data from YouTube using the YouTube Data API v3, store it in MongoDB and a MySQL database, and finally query the MySQL database using Streamlit. The functionalities:

1. Imports:

Streamlit for creating the web application interface.
Pillow for image processing (potentially for loading a logo).
Google API Client library for interacting with the YouTube Data API.
Pandas for data manipulation (likely for converting data into DataFrames).
PyMongo for interacting with MongoDB.
pymysql and sqlalchemy for connecting and interacting with the MySQL database.

2. YouTube Data API Functions:

channelstats: Fetches channel details like title, description, view count, subscriber count, etc., based on the provided channel ID.
videstats: Retrieves video details like video IDs, titles, durations, view counts, comment counts, etc., for a channel's uploaded videos.
playlistdetails: Retrieves playlist details like playlist IDs and names for a channel.
commentdetails: Fetches comments for a given video ID.

3. MongoDB Integration:

Establishes a connection to MongoDB using the connection string and creates a collection named "youtube" in the "guvi" database.
mongodb: Inserts the scraped channel data (Datalake) into the MongoDB collection.

4. MySQL Integration:

Connects to the MySQL database using credentials and creates a database named "youtube" if it doesn't exist.
SQLinsert: Fetches data for a specific channel ID from MongoDB and inserts it into separate tables ("channel", "video", "playlist", "comment") in the MySQL database.
databasestructure: Defines the structure of the tables in the MySQL database, including data types and foreign key constraints.

5. Streamlit App:

Creates a dropdown menu with options like "Home", "Channel Data Scraping", "Migrate to SQL", and "Queries".
Based on the selected option, performs the following actions:

Home: Displays a description of the project.

Channel Data Scraping: Allows users to enter a channel ID, scrapes data using the YouTube Data API functions, and displays basic channel information. It also inserts the scraped data into MongoDB.

Migrate to SQL: Allows users to enter a channel ID, retrieves data from MongoDB for that channel, and inserts it into the MySQL database tables. Additionally, it defines the table structure.

Queries: Provides a dropdown menu with various SQL queries to be executed on the MySQL database. Upon selecting a query, it fetches data and displays it using the tabulate library.
Overall, this code effectively demonstrates data scraping from YouTube, data storage in MongoDB and MySQL, and data querying using Streamlit.

This concludes, the project successfully built a web application that interacts with YouTube data using the YouTube Data API v3. 

Here are the key achievements:
Data Scraping: The application can scrape various data points from YouTube channels, including channel details, video details, playlists, and comments.
Data Storage: Scraped data is stored in two databases: MongoDB for initial storage and easier manipulation, and MySQL for structured storage and efficient querying.
Data Visualization: Streamlit provides a user-friendly interface for interacting with the application. Users can select functions like scraping YouTube data, migrating data to MySQL, and even querying the MySQL database.
