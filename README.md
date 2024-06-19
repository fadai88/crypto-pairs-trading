# crypto-pairs-trading
There are several approaches to pairs trading. Distance method is one of most popular ones among them. Its basic idea is simple and intuitive. First, we split price data into formation and trading periods. The next step is to normalize prices. Then employing Euclidian distance on the normalized price data, we select asset pairs with the least SSD (sum of squared differences). Mathematically it can be expressed as
![image](https://github.com/fadai88/crypto-pairs-trading/assets/12747028/9f36c49c-e1d5-4690-8f56-9b7d55d3308e)


The trading rule is that if the price difference between two pairs of a selected pair exceeds a predefined threshold, e.g., 2 standard deviations, we open a long or short position based on the value of the price deviation. The idea is that if two securities moved closely in the past – that is what SSD measures – then if they deviated from their historical ratio, we can expect that they will converge.

Trading signals will be generated based on z-scores. Z-score is a metric measuring how far from the mean a data point is. Z-scores are expressed in standard deviations. If z-score is over the preset threshold, which is 2, we short that pair. If z-score is below -2, we long it. If z-score is between -2 and 2, we do nothing. We close a long position if it is above 0; we close a short position if it is below 0.
