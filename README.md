# Data Challenge

Here is the data challenge from YosemiteLabs. Working here, we expect you to learn new things and do a lot of research. We aim at big projects that might have complex challenges, and this test should give you an idea on what we expect you to do.

To accomplish the challenge, you should download this SQLite database file: [https://drive.google.com/file/d/1tuV2rurY0RiW-ZxseRuMh8LMyRJeTYTh/view?usp=sharing](https://drive.google.com/file/d/1tuV2rurY0RiW-ZxseRuMh8LMyRJeTYTh/view?usp=sharing)

## Objective

You'll be working with public Brazilian Companies data structured in a SQLite database, and will be doing analysis of this data. You should deliver:

- A SQL script that creates a View containing the number of stores per state
- Python script that plots a chart of number of stores by the month that they started
- Python script that presents the average of stores by `root_cnpj`
- Any other chart or data that you may want to present to us (that's an extra and is not required for the test)

## Context on the data

Brazilian companies are represented by a document called CNPJ. The CNPJ has three parts:
- `root_cnpj`: The first 8 digits, represents a company
- `order_cnpj`: The next 4 digits, represents a store in real life
- `verify_cnpj`: The next 2 digits, just to validate if a CNPJ is a real one

If you take McDonald's for example, it will have one root_cnpj across all stores, but every individual store should have its own order_cnpj, like:
- 12488173000180
- 12488173000280
- 12488173000380

You can see above that all CNPJ's share the same root (12488173) but have different order (0001, 0002, 0003). This should mean that We're talking about the same company (McDonald's) but at different places (Like Sao Paulo, Rio de Janeiro, etc.). The last part (80) is irrelevant for the analysis.

The other fields are public information about the company, like its address, owner name, name, phone and so on

## First challenge

First challenge is to do a SQL script that creates a View aggregating the number of companies per `state`. For that, you should concatenate the whole CNPJ into one key and use that to count how many stores Brazil have per state (Like SP (Sao Paulo) or RJ (Rio de Janeiro)). We're going to run your script to create the view in our version of the database, and querying the view to see if the data is correct.

We expect a .sql file with a create view statement inside it.

## Second Challenge

For this you should be able to use Python to run an analysis of the data. You can combine your SQL skills with this challenge to prepare the data for plotting. You also can use any framework / library to plot the chart. If you don't know one, take a look at Matplotlib.

Python has starndard bindings to connect an query SQLite, so you can use that. We expect a script that when executed, shows a chart (can be a bar chart but not required) where X axis will be the Month and Year that the company started (like December/2020 or 2020-12 or any other format that you want), and in the Y axis will be the count of companies in that started in that month.

The column that represents the start date of the company is called `start_date`

We expect a .py file with the logic inside it. If you use external libraries. we expect a requirements.txt with the dependencies as well.


## Third Challenge

For this one, we want to evaluate your knowledge of Python functions and frameworks. You should build another script that connects and retreive the database data, and for each company (represented by `root_cnpj`) we want the average of stores (remember that one row is one store) in the database. So for our previous MCDonald's example:

- 12488173000180
- 12488173000280
- 12488173000380

They are all same root_cnpj but three different stores. The average here is 3.

Like the second challenge, you can combine your SQL Skills with Python to achieve the result.

You don't need to plot anything, just print the number at the end.

We expect a .py file with the logic inside it. If you use external libraries. we expect a requirements.txt with the dependencies as well.

## Conclusion

SQL Handling and Python scripting are necessary skills for a Data Analytics person that works in a tech based company. So the challenge here is in the way that we expect for you to do on a day to day work:
- Connect to our databases and systems
- Extract relevant information
- Present that in some Business Intelligence System

To accomplish this we suggest:
- Take a look at the SQLite Documentation for examples
- Take a look at the `sqlite3` official python package documentation
- Take a look at the Matplotlib (or your plotting framework of preference) documentation

The challenge should be done in 1 week, and the result should be sent to brenno@yosemitelabs.com with copy to diane@yosemitelabs.com.

Happy coding!
