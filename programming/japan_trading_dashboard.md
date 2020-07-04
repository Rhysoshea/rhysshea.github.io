---
title: Japan Trading Dashboard
layout: article
keywords: projects
summary: "Snapshots of Japan Trading Dashbaord"
permalink: /japan_trading_dashboard/
tags: [projects]
---

##### These images are taken as snapshots from a dashboard I set up as part of our trading platform for Japanese Power Futures. The dasboard was setup with Grafana, pulling data hosted on Postresql with data collected and parsed using Python.

##### Data includes: Japane weather forecasts, powerplant outage schedules, spot price for East and West Japan power contracts, LNG, oil and coal markets, and stochastic power price and demand forecasts based off machine learning techniques (Certain information ommitted for commercial sensitivity)


<div>
    <p> Price forecast at daily granularity </p>
    <img src="/images/daily_price_forecast.png" />
    <br/>
    <p> Demand forecast at monthly granularity</p>
    <img src="/images/demand forecast.png" />
    <br/>
    <p> Oil, gas and coal market prices and power spreads between baseload and peakload</p>
    <img src="/images/fuels.png" />
    <br/>
    <p> Powerplant outage schedules </p>
    <img src="/images/powerplant_outages.png" />
    <br/>
    <p> Over the counter orders and an artificial orderbook of broker orders </p>
    <img src="/images/otc_orders.png" />
    <br/>
    <p> Powerplant outage in table format </p>
    <img src="/images/outage_table.png" />

</div>