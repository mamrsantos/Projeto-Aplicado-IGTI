# Desafio_Chama



### The Flame system

<p align = "justify">It calls is a marketplace that brings together consumers looking for gas bottles with dealers thatsell those bottles. Each dealer has its own service area: a polygon drawn on the map to indicatethe region where it wants to deliver gas. Whenever a consumer opens the app, he or she willSee the list of gas offers based on the intersection of those service areas. The Flame App allowsthese users to compare based on price, rating, ETA (estimated time of arrival), and badges(visual highlights of dealers that meet certain excellence criteria)</p>

<p align = "justify"> Once the user selects his favorite choice, he can place an order. The dealer then is notifiedabout this new order and can accept or decline it. However, if he takes too long to react to theorder, the customer might cancel the order. On a happy journey, the bottle is delivered withinthe ETA and the customer can rate the delivery.</p> 

<p align = "justify">One of the major recent changes in the Flame ecosystem was the introduction of the mobiledealer concept. Unlike regular shops (with territorial models), these dealers are drivers that usea driver app to receive orders, and only consumers that are close to the driver would be able tosee him or her in the offer list.</p>  

**goal**

The main purpose of this case is to assess your knowledge, technical skills and how you think.

The most important part is to show your line of thinking.

The case is divided into two parts that represent typical tasks you would perform as a data

scientist at Flame

**Deliverables**

* Your code

* A short document explaining your steps and including any visualizations you've created

  to study the data or answer the question

**assessment criteria**

* Clarity of your code

* Feature engineering

* Clarity of your explanations </p> 

  

**Question 1 - Analysing experiment results**

<p align = "justify"> We have recently been testing an alternative model to determine how mobile dealers are displayed on the offer list, with the goal of improving their productivity. the default and alternative models are detailed below:</p>

* <p align = "justify"> Default model​: Consumers in a 2.5 km radius can see the mobile dealer. If an order isplaced, the focus point shifts to the consumer's location: only consumers in 2.5 kmradius from the first consumer's location would be able to see the mobile dealer. Therecould only be a maximum of 2 concurrent orders at any given moment for a driver.</p>

* <p align = "justify"> Alternative model​: We use Google Maps to calculate travel durations between the mobiledealer's open orders and the consumer. We define the maximum stock of delivery time forthe mobile dealer, and only display the mobile dealer to the consumer if the total travelduration is below the maximum stock. There is no limitation of concurrent orders.</p>  
<p align = "justify"> We decided to start the experiment with a few mobile dealers and gradually increase thenumber of drivers in the alternative model.

After running the experiment for a while, a member of our Engagement team sends you aAsking about the impact of the alternative model on productivity. In order to preparethis analysis, we have given you access to a Google BigQuery project where you will find thetable DataScience-case.Experiment.MobileDealer , containing information about performancemobile dealers. Column descriptions can be found in the table schema. </p> 

**Question 2 - Feature engineering**

<p align = "justify"> One of the key parts of a user journey in the Flame app is selecting a dealer. After inputtingtheir address, the user faces a list of dealers that deliver in their location. the list displaysdealers that are open and/or closed, their prices, brand, rating, ETA and their badge (ifapplicable).</p>

<p align = "justify">Users can then select a dealer from this list and place an order. This is our main conversionmetric at Chama, which we closely monitor and continuously try to improve.</p>

<p align = "justify">You are approached by management to prepare a study about the key factors that lead users toconvert, and how we could predict which dealer (if any) would be chosen from the offer list.
</p>
<p align = "justify">As you know, a good ML model can only come from good feature engineering. Your task is twofold:</p>

1.  Create, **using only a SQL query** , features That You could use in the model. 

   You are expected to create features that could be potential predictors of a conversion model.

   We would like to assess BOTH your creativity to think about **new features** That Could model the

   consumer's decision process and your **ability technical** to calculate These features using SQL.

2. From the preliminary visualization and selection feature **(with Python or R)**

Note That You are **not** required to train the model. On the Google BigQuery project you will find

two datasets:

* *DataScience-case.Conversion.TrainingSet* - contains data from offer lists, with the label

  "Ordered" indicating if that offer item led to a conversion

* *DataScience-case.GeographyBrazil.CityState* - contains geographical date on Brazil

**Hints**

* The SearchId is a very important column, since it ties together results that were shown in

  the same offer list

* Try to put yourself in the shoes of a consumer: how do you compare list items in your

  life? What are factors you take into account when making a decision?
