# Descriptions of Startups

Good description of startup is like a little elevator pitch that can help starup to skyrocket, while the bad one...

> Hypothesis 1: It seems like with time coming we started to recieve longer and longer description? Is it true? If yes, what are the possible reasons? 

First try: let's just do the scatter plot  with **year <-> length of description**

![How year and the length of description are connected](./images/output.png)

Well, we can see that with time coming we *do* have longer descriptions, although still a lot of themm fall in the category **Length around 500 tokens**

Let's try to plot the mean values:
![How year and the length of description are connected](./images/boxplot2.png)

Here we can see that although during the time period 2005-2010  our mean value was more unstable, since 2011 it was fluctuating around 400.

Also, we can notice that mean length is slightly decreasing throught our time period.

So, we can reject our Hypothesis for now.

However, let's additionaly investiagty how lengths were different from 500 (our hypothesesed "ideal" length)

![How year and the length of description are connected](./images/2.png)

In average, we get 200 tokens difference.

> Hypothesis 2: Maybe if we cluster our data to two clusters w.r.t to the length, we will be able to analyse everything withing clusters?


![Picture 3](./images/clusters.png)

Here I plot median and mean value for both clusters. 
What we see - for small cluster mean and median are virtually the same and equal to 300 tokens.

For longer ones, due to outliers, mean is pretty distant from median, and median is equal to 841, while mean is 949.