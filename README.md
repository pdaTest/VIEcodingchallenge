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

The exercise consists of two separate, independent parts (with two input files). You can use code lines for both parts and resolve them independently.


=> Inputs

Each of the two inputs files contains similar information, namely:

• Load: the load is the amount of energy (MWh) that needs to be delivered during any single hour.

• Fuel costs: based on the cost of the fuels of each power plant, the merit-order of the portfolio can be determined.

- Gas (euro/MWh): the price of gas per MWh. If the gas price is at 6 euro/MWh and the efficiency of the powerplant is 50% (i.e. 2 units of gas will generate one unit of electricity), the cost of generating 1 MWh is 12 euro.
- Kerosene (euro/MWh): the price of kerosene per MWh.
- Co2 (euro/ton): the price of emission allowances (to be taken into account only optionally, not mandatory for the exercise).
- Wind (%): wind coefficient. Example: if there is on average 25% wind during an hour, a wind-turbine with a capacity of 4 MW will generate 1 MWh of energy.

• Power plants: describes the assets at disposal to generate the demanded load. For each power plant, the information specified is the following:

-	Name
-	Type: gas fired, turbojet or wind turbine.
-	Efficiency: the rate at which they convert a MWh of fuel into a MWh of electrical energy. Wind turbines do not consume fuel and thus do not to incur any fuel costs.
-	Pmax: the maximum amount of power the plant can generate.
-	Pmin: the minimum amount of power the plant generates when switched on.

• Market spot prices (only for part 2).


=> Test
The response should be as clean as possible. You can devise any type of output to display your results (data frame, an Excel spreadsheet sorted by a Python command, a sentence printed via Python, etc.). Keep in mind that, as an operational team, the recipient should be able to interpret results quickly. We will evaluate the quality of your code.

Part 1:

1.	Determine the merit order of the portfolio.
2.	Specify the power output of each asset in order for the portfolio to cover the given load and maximize its total revenues.

Part 2:

For this part, the commitment of the portfolio is independent of the load. The load can be covered by either buying the necessary energy from the market or, else, scheduling the assets to cover the load. In addition to that, assets can be scheduled to produce power up to their maximum capacity (and beyond the required load).

1.	Determine an hourly production plan that maximizes overall portfolio revenues.
2.	Display the position of the power plants (MWh) on the market for each of these hours.
3.	Display the hourly cash flow for each asset as well as the hourly and the daily cash flow for the entire portfolio.

