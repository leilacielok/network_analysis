# network_analysis
For this network analysis, data from Twitter of the Congressional network was used.
The dataset was collected using the Twitter API and is available at: https://snap.stanford.edu/data/congress-twitter.html.

This dataset was posted by Christian G. Fink, Gonzaga University (finkt@gonzaga.edu)

congress_network_data.json contains the following data:

* inList: list of lists such that inList[i] is a list of all the nodes sending connections TO node i
* inWeight: list of lists containing the connection weights (transmission probabilities) corresponding to the connections in inList
* outList: list of lists such that outList[i] is a list of all the nodes receiving connections FROM node i
* outWeight: list of lists containing the connection weights (transmission probabilities) corresponding to the connections in outList
* usernameList[i] gives the Twitter username corresponding to node i

congress.edgelist contains the weighted, directed edgelist for the Congressional network, in NetworkX format
