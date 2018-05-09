# Deep Sequence Learning with Auxiliary Information for Traffic Prediction. KDD 2018 (Accepted).

### Binbing Liao, Jingqing Zhang, Chao Wu, Douglas McIlwraith, Tong Chen, Shengwen Yang, Yike Guo, Fei Wu

###### Binbing Liao and Jingqing Zhang contributed equally to this article. 

## Contents

1. [Abstract](#Abstract)
2. [Model](#Model)
3. [Dataset](#Dataset)
4. [Experiments](#Experiments)
5. [Installation](#Installation)
6. [Citation](#Citation)
7. [Poster and Video](#Poster)

<h2 id="Abstract">Abstract</h2>
Predicting traffic conditions from online route queries is a challenging task as there are many complicated interactions over the roads and crowds involved. In this paper, we intend to improve traffic prediction by appropriate integration of three kinds of implicit but essential factors encoded in auxiliary information. We do this within an encoder-decoder sequence learning framework that integrates the following data: **1) offline geographical and social attributes**. For example, the geographical structure of roads or public social events such as national celebrations; **2) road intersection information**, i.e. in general, traffic congestion occurs at major junctions; **3) online crowd queries**. For example, when many online queries issued for the same destination due to a public performance, the traffic around the destination will potentially become heavier at this location after a while. Qualitative and quantitative experiments on a real-world dataset from Baidu have demonstrated the effectiveness of our framework.


<h2 id="Model">Model</h2>
model


<h2 id="Dataset">Dataset</h2>
We collected a large-scale traffic prediction dataset --- Q-Traffic dataset, which consists of three sub-datasets: query sub-dataset, traffic speed sub-dataset and road network sub-dataset. We compare our released Q-Traffic dataset with different datasets used for traffic prediction.

### Query Sub-dataset
This sub-dataset was collected in Beijing, China between April 1, 2017 and May 31, 2017, from the [Baidu Map](https://map.baidu.com). The detailed pre-processing of this sub-dataset is decribed in the paper. The query sub-dataset contains about 114 million user queries, each of which records the starting time-stamp, coordinates of the starting location, estimated arrival time-stamp, coordinates and query word of the destination. There are some query samples as follows:

<code>
aaa, bbb, ccc, ddd, eee  

aaa, bbb, ccc, ddd, eee
</code>

### Traffic Speed Sub-dataset
We also collected the traffic speed data for the same area and during the same time period as the query sub-dataset. This sub-dataset contains 15,073 road segments covering approximately 738.91 km. Figure 1 shows the spatial distribution of these road segments, respectively.  

![Spatial distribution of the road segments in Beijing](https://github.com/JingqingZ/BaiduTraffic/tree/master/fig/beijing_road_seg_compressed.png)

They are all in the 6th ring road (bounded by the lon/lat box of <116.10, 39.69, 116.71, 40.18>), which is the most crowded area of Beijing. The traffic speed of each road segment is recorded per minute. To make the traffic speed predictable, for each road segment, we use simple [moving average](https://en.wikipedia.org/wiki/Moving_average) with a 15-minute time window to smooth the traffic speed sub-dataset and sample the traffic speed per 15 minutes.
Thus, each record is represented as road_segment_id, time_stamp, traffic_speed.

There are some traffic speed samples as follows:

<code>
id, time, speed  

id, time, speed 
</code>

### Road Network Sub-dataset
Due to the spatio-temporal dependencies of traffic data, the topology of the road network would help to predict traffic. Table 2 shows the fields of the road network sub-dataset. 

![Table 2. Examples of geographical attributes of each road segment.](https://github.com/JingqingZ/BaiduTraffic/tree/master/fig/road-network-subdataset.png)

For each road segment in the traffic speed sub-dataset, the road network sub-dataset provides the starting node (*snode*) and ending node (*enode*) of the road segment, based on which the topology of the road network can be built. In addition, the sub-dataset also provides various geographical attributes of each road segment, such as width, length, speed limit and the number of lanes. Furthermore, we also provide the social attributes such as weekdays, weekends, public holidays, peak hours and off-peak hours.


<h2 id="Experiments">Experiments</h2>
experiments


<h2 id="Installation">Installation</h2>
installation


<h2 id="Citation">Citation</h2>
In case using our dataset, please cite the following publication:  

<code>
    @inproceedings{bbliaojqZhangKDD18deep,  

    title = {Deep Sequence Learning with Auxiliary Information for Traffic Prediction},  

    author = {Binbing Liao and Jingqing Zhang and Chao Wu and Douglas McIlwraith and Tong Chen and Shengwen Yang and Yike Guo and Fei Wu},  

    booktitle = {Proceedings of the 24th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining},  

    year = {2018},  

    organization = {ACM}  

    }  
</code>


<h2 id="Poster">Poster and Video</h2>

- You can find our KDD 2018 poster here.

- You can find our KDD 2018 Video here.
