# Supply_Chain_Analytics
![Supply Chain Analytical video](supply.jpg)
## Executive Summary
Supply chain analytics is a crucial component of modern businesses seeking to optimize their operations and enhance overall efficiency.
Supply chain analytics involves the use of data and advanced analytics tools to gain insights, make informed decisions, and improve the performance of a company's supply chain. It encompasses a wide range of activities, from demand forecasting to inventory management, transportation optimization, and supplier performance analysis.

In this project of mine I wont only categorize supply chain under the manufacturing zone, supply chain touches procurement, logistics and other corporate sectors. My focus will be more on the procurement zone. Procurement on its own is a critical component of supply chain management process. Procurement specifically refers to the process of acquiring goods & services.

That been said above, let's head right into our supply chain analytics projects.

The Supply Chain begins with the producers of raw materials and ends with the product being delivered to the consumer. In this project we will be more of the consumer side. so lets dive in to one of the terms that will help us in the supply chain ecosystem.

## What is Make Vs Buy
“Make Vs Buy” is a strategic decision-making process that organizations go through when determining whether to produce (make) a product or component in-house or to purchase (buy) it from external suppliers. This decision has significant implications for cost, quality, time-to-market, and resource allocation.

## The Problem Statement

The company is into production of generators, spare parts and servicing. Your task is to create analyses that help the company determine make vs buy decision for many of their products they use in servicing their generators. The management has already requested quotes from the suppliers. Lets look at the data that we will be using for this analysis.


![Supply Chain Analytical video](data.jpg)


From the image above we can see the numbers of tables we will be working with. The scenario volume, scenario volume(All), supplier yield, are not the raw data, those are table created to support our analytics context.

Lets explore the quote data in detail.
Quotes :
I remember when i was still little, any time my mum sent me to the market, she always gave me a list of things to buy, with their prices, she will tell me the shops to go and the one not to go, so in essence she has done her own analysis. This was done to avoid stories that touches, though they will still be stories from me at the end of the day. So lets look at quotes as the list of things to buy.

Definition : Quotes refers to a formal document provided by a supplier to a potential customer or buyer. This document outlines the pricing, terms, and conditions for the products or services that the supplier is offering. Quotes are an essential part of the procurement or supply chain process, as they allow buyers to compare different suppliers and make informed decisions based on factors such as cost, quality, and delivery time.
They essentially say “ if you buy X volume of this part, you will need to pay Unit Cost per unit and a one-time cost equal to NON-reoccurring expenses.

Quotes are specific to the product, volume and supplier. So in that case for supply chain decisions, it does not make sense to aggregate these fields. So I will set the volume columns in Power Bi, which has summarization set to default to Don’t summarize.

Lets create a visualization displaying all of the fields in the quote table, with a column chart that shows the number of unit price quotes provided for each part number.


![Supply Chain Analytical video](Supplier_Selection.jpg)

The image above showcases my supplier selection visualizations dashboard, The sole purpose of this dashboard is to help you determine the best option in the case of suppliers that you can choose to supply the products you need for your services. There are about 7 visualization in the supplier selection dashboard, which will be broken down for further explanations.

They are :

Cost breakdown
Sum of unit cost by volume and supplier.
Sum of non reoccurring expenses by volume and supplier.
A card visual that shows the lowest cost supplier
A volume and a part number slicer
and a table visual, that consist of part number, part name, sum of unit cost etc.
let me try to break down some of the terms that i will use that are related to supply chain:

Unit cost: This is the cost associated with producing or procuring a single unit of a product.

Extended cost: The cost paid for the products only (does not include onetime expenses)

Extended Cost = (Unit Cost) * (Quantity of Units Purchased)

Non-recurring expenses: One-time costs required to enable production. Non-recurring expenses are generally not part of the regular ongoing operational costs of an entity. Instead, they arise from special circumstances or events.

Common examples of non-recurring expenses

• Legal fees
• Engineering expenses for production set-up
• Minimum charge to occupy manufacturing equipment.
• Currency exchange losses or Gains
• Environmental Cleanup cost

Full Cost
The total amount a company must pay to buy a certain quantity of products
Full Cost = Extended Cost + non-recurring expenses
Or
Full Cost = (10000 per gallon * 10gallons) + 65000 set-up fee = 165000

![Supply Chain Analytical video](full_cost.jpg)


Visualizing lowest cost supplier
Scenario

My line manager has asked for a report page that shows :

The suppliers name with the lowest full cost for a part number and quote volume combination.
The full cost breakdown by extended cost and full cost.
Visibility to all of the other supplier quotes and full cost for the part number.
To use a card visualization that shows lowest full cost supplier for the part number & volume combination
All of these instructions and recommendation has been done on fig 3. but lets try to solve a problem.

Management are asking for something specific, like; what is the lowest full cost for a part number of P1010 on a volume of 2000.

To answer the question above:

The lowest cost supplier for part number P1010 on a volume 2000 is ATZ , we can also see it has the lowest non reoccurring expenses on the 2000 volume mark. In my opinion and based on this analysis we will all go for ATZ.

You can view the dashboard & interact with it here :https://app.powerbi.com/reportEmbed?reportId=0e909fee-aed2-490b-8f5e-36b6eed57236&autoAuth=true&ctid=e1e4f47f-4370-4de4-8a71-48984d434887

Creating a volume parameter and scenario analysis
We will explore building a scenario analysis tool to examine how our cost calculations change as volumes change.

![Supply Chain Analytical video](Scenario_analysis.jpg)

Note:
In reality its highly unlikely to order the amount of product that was quoted.
Projects start with assumptions, so analysis tools should adjust to this uncertainty

Scenario & volume changes
What if our production estimate does not match the quoted volume. To be honest, things are not that straight forward as I made it seem earlier. Because it is highly unlikely to order the exact numbers that were quoted. That is where the scenario analysis comes in.

All projects starts with uncertainty, sources of uncertainty are :
• Demand
• Product market fit
• External economic conditions
• Price

In fig 4 we created a scenario volume parameter. This will make the report dynamic. Parameters adds a user-controlled slicer to the report. you can find it on the top right corner.

This will help to identify how the cost calculations changes and in the dashboard it shows how the full cost changes across different potential production volumes.







