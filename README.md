### Analysis 
#### Investigate the Data
The first thing I did was open the file in Sublime Text to understand the file format. This let me know the data was tab delimited and had a header row.

I used a Jupyter Notebook for the next steps. You can find that notebook here:
[https://github.com/wdbroen/shootproof/blob/master/Data%20Investigation.ipynb](https://github.com/wdbroen/shootproof/blob/master/Data%20Investigation.ipynb)

I loaded the data into a Pandas Dataframe for a high level understanding of what was going on in the data.

Most columns do not have null data, but the billing state and country is missing for a large number of records.
***
#### Create Grouping Level
The data did not have an easy way to group similar items for analysis. I noticed that each order item name had a category associated. This is always the last set of parenthesis in the item name. In order to extract that category I wrote a function to reverse the string, find the last set of parenthesis, extract the category, and reverse the string back to normal. I named this field *item_category*
***
#### Data Integrity Issues?
The *order_grand_total* does not match the sum of the *order_item_total_price* for each order. It does not line up by including shipping costs either. This was a big red flag for me. It is situations like these that can lead to inaccurate reporting.
****
#### What is the question?
When working with dataset for the first time I try to figure out what questions can the data answer.

 - **Who**
		 - The data does not have a customer_id or any unique identifier of who placed the order.
		 - This prevents identifying the most valuable customers
 - **What**
	 - The data has a record for each order_item
	 - Order Item measures:
			 - order_item_quantity
			 - order_item_unit_price
			 - order_item_total_price
			 - order_item_bounds
	 - Because of the issue between order_item_total_price and order_grand_total mentioned above, I am assuming that the order_item_total_price is the most accurate for this exercise because the data is at an order item level.
 - **When**
		 - Every *order_created*  is October 1st or October 2nd in 2015
		 - The *event_created* dates range from 3/11/13 - 10/1/2015, but are too sporadic to have confidence in their relevance.
 - **Where**
		 - The data has well populated *shipping_state* and *shipping_country* fields
		 - The data has semi-populated *billing_state* and *billing_country* fields
		 - I made the assumption that these fields refer to the same customer
 - **Why**
		 - There are no data points to support why someone placed an order

I was hoping to use this dataset to look into some of the items I spoke with Brian about on the phone. Unfortunately there are not enough attributes to look into lifetime value of a customer, customer churn, or month over month item trends.

The questions that can be answered are
		- Where are customers ordering from?
		- What items are performing best?
***
#### Visualize the Data
I used Tableau as my data visualization tool. The dashboard is available here:
[https://public.tableau.com/profile/will.broen#!/vizhome/OrderItemData/ItemCategorySummary](https://public.tableau.com/profile/will.broen#!/vizhome/OrderItemData/ItemCategorySummary)
*(There is another dashboard on my public Tabeau account for a similar project for a company named CallRail)*

I used the created *item_category* field to bucket similar items in order to have a manageable number of items on a graph. The 3 metrics are easily sortable to quick identify which categories are responsible for the most revenue, order counts, or revenue per order.

The other dashboards show where customers are ordering from at either a Global or United States view. The United States view allows the user to select to measure $ or # of orders.

When end users are involved I like to create dashboards using the INSIGHT project management style. It is essentially the Agile process using a forced acronym.
 - Identify Question
 - Name KPIs
 - Shape Data
 - Initial Concept
 - Gather Feedback
 - Hone Dashboard
 - Tell the Story
***
#### Actionable Insights
This was primarily a descriptive analysis due the available data points. 

Some ways this data could be enhanced to provide prescriptive analytics are:

 - Increase the date range of the data to identify trends and growth pattens
 - Include customer level information. Determining high value customers can make sure resources are aligned to best service those customers.
 - Increasing the date range and adding customer level information will allow you to identify repeat customers vs 1 time customers. These segments can be targeted with different marketing campaigns.
 - Rethinking the item categorizing strategy. Bucketing similar items with a consistent field could enable identifying item upsale opportunities
 
