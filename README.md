## PDA TEST

# Welcome ! 

In this page you can find the description of a coding challenge that we ask people to perform when applying for a VIE position in our team. This test is not only a coding challenge but also some knowledge around the energy markets will be useful. 

The goal of this coding challenge is to provide the applicant some insight into the business we're in and as such provide the applicant an indication about the challenges she/he will be confronted with. Next, during the first interview we will use the applicant's implementation as a seed to discuss.

# Role description:

The role consists of providing quantitative analytical support to all market operations ran by the Power Day-ahead (PDA) team of Engie Global Energy Management (GEM) in Brussels. The PDA team is in charge of bidding the capacities of the Engie power plant portfolios on the DA exchanges of all Central Western Europe (CWE) countries. This includes setting up optimal strategies that emphasize the use of smart bidding products and that result in schedules for each plant that maximize revenues, ensure physical balance and compliance with market rules.

An important part of the operations is related to ancillary services. PDA also ensures the bidding of all ancillary capacities available in the portfolios on the reserve tenders organized by national TSOs. This tender activity is evolving fast, with new products and more frequent deadlines becoming the norm in CWE. There are ongoing efforts to improve the current processes (and develop new ones where applicable) that enable PDA to cost and price these contracts, but there remains a strong need for analytical support and market follow-up.

# Projects on the pipeline:

The VIE role is expected to contribute to the most pressing projects currently at work at PDA:
-	Ancillary Services in Day-ahead (ADA) for Belgium and the Netherlands
This project consists of supporting the ongoing developments to set up the costing and pricing processes to enable the bidding of the FCR, aFRR and mFRR capacities on the four daily tenders in Belgium and the three in the Netherlands, all expected to be live by the end of September 2020.
Additional developments expected on this project are:
o	A KPI on the bidding strategy for ancillary contracts that allows benchmarking and improving these strategies.
o	An automated process computing a day-ahead/intraday risk factor to account for intraday risks (including optimal activation strategies) in the pricing of day-ahead contracts.
-	Genius algorithm for the automated bidding of thermal and pump-storage assets on the spot market
This projects consists of supporting the improvement of the existing Genius algorithm. The algorithm outputs scenarios for the bidding of thermal assets (namely CCGTs and coal-fired plants) on the day-ahead auctions (energy). Foreseen improvements of the algorithms are:
o	The accounting for contracted ancillary services on the assets being bid, so that the scenarios proposed ensure the delivery of said contracts.
o	An extension of the algorithm to put forward scenarios for the pump storage assets in the portfolio.

Depending on the progress made by the team on these projects and any other needs that may arise, the VIE role may be required to contribute on other topics.

Operational support:

All market operations performed at PDA are organized in shifts. Subject to availability and to the interest of the candidate, the VIE role may be extended to include training to perform any of these shifts.


# Rules of the coding challenge : 

There a two different parts with two input files.
The two parts are completely independents but feel free to code whatever you want. You can use some code lines for both parts. If you have some problems for one of these parts it is not a blocking point for the other one.

=> Inputs

Each of the two inputs files contain the same kind of information such as: 

•	Load: the load is the amount of energy (MWh) that need to be generated during one hour.

•	Fuels: based on the cost of the fuels of each powerplant, the merit-order can be determined which is the starting point for deciding which powerplants should be switched on and how much power they will deliver. Wind-turbine are either switched-on, and in that case generate a certain amount of energy depending on the % of wind, or can be switched off.

- Gas (euro/MWh): the price of gas per MWh. Thus if gas is at 6 euro/MWh and if the efficiency of the powerplant is 50% (i.e. 2 units of gas will generate one unit of electricity), the cost of generating 1 MWh is 12 euro.
- Kerosene (euro/MWh): the price of kerosene per MWh.
- Co2 (euro/ton): the price of emission allowances (optionally to be taken into account).
- Wind (%): percentage of wind. Example: if there is on average 25% wind during an hour, a wind-turbine with a Pmax of 4 MW will generate 1MWh of energy.

•	Powerplants: describes the powerplants at disposal to generate the demanded load. For each powerplant, is specified:
- Name
- Type: gas fired, turbojet or wind turbine.
- Efficiency: the efficiency at which they convert a MWh of fuel into a MWh of electrical energy. Wind-turbines do not consume 'fuel' and thus are considered to generate power at zero price.
- Pmax: the maximum amount of power the powerplant can generate.
- Pmin: the minimum amount of power the powerplant generates when switched on.

•	Market Spot Prices (only for Part 2).


=> Test

The response should be cleaner as possible. You could imagine any kind of outputs to displays your results (Dataframe, Excel sorted by a python command, sentence printed via python…) but do not forget that as an operational team, we like some clear information. Moreover, you can code as you want but be careful because we will be very sensitive to the quality of your code.


Part 1 : 

1)	Determine the Merit Order of this virtual economics area.
2)	Classify the plants from the cheaper one to the most expensive in terms of power production.
3)	Specify for each powerplant how much power it should deliver to have a portofolio which matchs exactly the given load. 

Part 2 :

For this second part, we make the following assumption : you can do whatever you want with the production of the assets. That is to say, we assume that we do not have any technical constraints and we can produce at Pmax at a certain hour and to stop the production the next hour easily.

1)	Determine an hourly production plan which maximizes our P&L in these economic conditions. 
2)	Explain our positions on the market for each of these hours. 
3)	Display the hourly P&L for each assets, then the hourly and the daily P&L for the entire portfolio.

