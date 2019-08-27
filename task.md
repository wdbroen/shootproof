# Data and Analytics Exercise

# Overview

Here at ShootProof, we prefer to have a good idea of a candidate's technical
experience and analysis skills before proceeding with portions of our recruiting
process.  We believe that the exercise below will illustrate a candidate's
approach to working with technologies and methodologies that may be commonly
used in our data and analytics engineering team here at ShootProof.

# Guidelines

* This exercise should not take you more than two hours to complete. If
  your solution is taking longer, that's okay—be honest and let us know how long
  it took and why you think it took that long.
* Be as thorough as you wish.
* All exercises are to be performed as if you were on the job.
* You may submit your response in one of the following ways:
  * Package an archive (ZIP, tarball, etc.) of your files and deliver it to
    your contact.
    * If working with a recruiter, deliver it to them.
    * If working with ShootProof directly, deliver to <careers+dae@shootproof.com>.
  * Fork our repository and open a pull request.

There are no right or wrong answers.  We are deliberately offering creative
freedom and interpretation to all candidates who are completing this exercise.
You would receive similar tasks on the job and would be given similar latitude
with how you approach the problem and deliver business insights.

# Exercise: Communicate business insights from raw data

First, let's talk about our domain models:

* **Order**: an order represents a set of prints, digital downloads, etc. placed
  by a customer's end client.  An order always contains one or more order items.
* **Order Item**: an order item is a single item in an order.  It has metadata
  such as a name, price, and quantity.

In this repository, you'll find a `order-item-data.csv` file.  It contains a
data set with one row per order item.  You will find `order_id` and
`order_item_id` values, along with additional values on the order and order
items.

## Your task

This is a data set that represents real world cases you would find at
ShootProof.  Using this data set, provide some business insights that you are
able to glean from this data.

For example, you may consider activities such as:

* Loading the data into a relational database.
* Writing SQL queries against the relational database to extract information.
* Use a tool like [Gnuplot](http://www.gnuplot.info/), [matplotlib](https://matplotlib.org/),
  [Pandas](https://pandas.pydata.org/) or similar to present interesting visualizations or relationships
  you observe in the data.

The business insights you provide are solely up to you; be as insightful and
creative as you would like.

Please provide your insights in any of the following forms:

* Paragraph-form explaining your insights
* Data visualizations

### Provide outline of steps you would use to ingest this data set

You may illustrate your approach to working with this data by including actual
command-line output, shell commands, etc.  Your data ingestion steps may be
replayable by the reviewer, but this is not required.

Describe why you would approach the ingestion of this data in the manner you
chose.
