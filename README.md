# BookBuddy
This is a revised version of my capstone project at GMU. This BookBuddy application was developed to assist an aspiring author in promoting the content of her new book. The application offers three key functionalities: (1) AI-powered image and text generation, (2) web scraping to analyze search trends based on user-provided prompts. (3) A business finance tracker that enables users to input and delete financial records while keeping track of monthly and total expenses.

This is the system overview that describes how to use the functions of Book Buddy. We start off with running the application in Visual Studio Code after successfully finish creating the .env file located in [book-buddy > server > .env]. It is best to copy and paste the keys into the correct location. Running the application on Visual Studio Code is most recommended. Open up two separate terminals in order to run both the front and back end systems. Start the back end server by navigating to book-buddy > server and running the command: node index.js. Then, start the front end server by navigating to > book-buddy and running the command: npm run dev.

With the AI Content Generator, once clicked you'll have the content generator dashboard and two options of either Text Generation or Image Generation. The files are automatically downloaded and stored into a folder. Images will be stored .png files in [book-buddy > server > output > images]. Text will be stored as .txt files in [book-buddy > server > output > text].

Image generation usually takes longer than text generation and the generation speed can vary depending on internet speed.

For the Web Scraper, any keyword such as book novel will be prompted inside of the text box and it will be looking at its popularity over the past couple of months. You can also switch from viewing a graph to looking at current, up-to-date search results.

The Business Finance Tracker helps users keep track of their company’s income and expenses in a clear and straightforward way. Users can add revenue or expense entries by choosing the type of transaction and entering the amount. Each entry is saved in the browser’s local storage, so the data stays available even after the page is closed.

The tracker shows up-to-date totals for revenue and expenses, along with a summary of activity from the past 30 days. It also calculates the net total to give a quick view of the business’s overall financial position. Users can review a full list of transactions with timestamps, remove individual entries if needed, and see how their balance changes over time through a line graph that updates as new transactions are added.

All information is stored locally on the user’s device. No external accounts or databases are required, making it a practical option for basic financial tracking and reviewing trends over time.
