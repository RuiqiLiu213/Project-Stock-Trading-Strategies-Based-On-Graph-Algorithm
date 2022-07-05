# Project-Stock-Trading-Strategies-Based-On-Graph-Algorithm

## Motivation
- Some existing work suggest peripheral(low centrality) stocks yield superior risk-adjusted returns compared to investing in the most central stocks, as the peripheral
stocks offer superior diversification benefit while central stocks suffer from huge collective exposure to market risks.  
- We use several graph algorithms to construct correlation relationship between SP500 component stocks, which is expected to have two results: 
  1. stock noise information is filtered by selecting edges from high to low correlation, 
  2. Centrality of single stock can be defined by the sum of its shortest path to all other nodes. smaller sum indicates the node is at the center of graph, thus has   higher centrality.  
- Back test 3 years investment, Redo the graph algorithm and update portfolio every month.  

## Description:
- Retrived and restructured historical S&P 500 components from https://en.wikipedia.org/wiki/List_of_S%26P_500_companies
- Use API to get historical price of active S&P components of each period.
- Design MST (Kruskal Minimum Spanning Tree), PMFG(Planar Maximally Filtered Graph), Full Connected graph algorithms.
- From 2019-06-01 to 2022-06-28, at the start of every month, find the active S&P 500 components at that time, caculate correlation matrix of these stocks.
- Constract graphs using correlation based on three algorithms, caculate centrality based on sum of shortest path, generate centrality rank in ascending order.
- Back test: Instest in all stocks, top 5 stocks and bottom 5 stocks at start of each month.

## Result:
