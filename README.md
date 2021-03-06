# IDEAS_FSS_Vis_project
## Visualization of the correlation of gas species concentration over time in Amazon

### Background and Motivation 
My research is mainly on the fundamental surface chemistry of atmospheric aerosols, but I’m also interested in complicated field samples that require a lot of data analysis to unravel the underlying physics. In 2014, a student in my group participated in the GoAmazon Field Campaign, in which she went to the Amazon rainforests with other scientists and collected aerosol samples. From vibrational spectral analysis, we found that some samples show a distinctive peak in a certain region that might be associated with a certain structural motif. Our hypothesis was that it might be related to sulfate groups being attached to the molecule. So, we gathered data on the concentrations of all kinds of gas molecules during that period of time at the same location (T3). I am hoping to see if there is correlation between the concentration of one or more of the gases and the amplitude of that distinctive peak. And, in general, it would be helpful to visualize the correlations, if any, between any of those gases.

I first tried using Plotly to quickly see the correlation matrix of some clean data that I had. Then I found Bokeh to be a very useful library for interactive data visualization. One of the samples in the Bokeh Gallery (demo: https://demo.bokeh.org/stocks; code: https://github.com/bokeh/bokeh/tree/master/examples/app/stocks) has the template that well fits how I would like to visualize my data. In addition, Bokeh is based on Python, which I am more familiar with. By using Bokeh, I have been able to focus on learning various functions in the library and understanding the logic of building the interactivity, instead of getting used to the syntax of a brand new language.

Overall, the coding process has been smooth and fun, with small challenges in almost every step. First, I implemented the template with some readily available clean data by following and understanding every line in the sample. Then, I played around and got familiar with the tools and styling functions, and added a line of text that updates with the time frame on selection. After that, I cleaned up all the data we collected and added them to the project. I also tried to add two histograms for the x and y axes of the correlation plot, but wasn't able to make it work in time. This will be my homework.

### Interface
![This is a screenshot of the interface](Interface_demo.png)

#### (After highlighting data in a certain time frame with the "Box Select" tool:)

![This is a screenshot of the interface](Interface_demo_selected.png)

The interface is very self-explanatory for users. On the widgets at the top-left corner, one can select two sample gases in the dropdown menu. The change of concentrations of the two selected sample gases over time will show up at the bottom, and the correlation plot will show up at the top-right corner. Pay attention to the tools on the side of each graph. One can zoom in and out, highlight data in a certain time frame by using the "Box Select" tool, and hover on data points to read the values. The table summarizes the mean and standard deviation of the concentration in the selected time frame. 

Because the data have not been published, in the notebook on the GitHub, I generated mock periodic time series data to demonstrate the template. Therefore, you might find the data "boring" without any correlations. This is only a demonstration of the interactive visualization tool. Real data will be uploaded after the research work is published.

### To Make It Work

1. Install bokeh with either 
```
pip install bokeh
```
or 
```
conda install bokeh
```
If you already have bokeh installed, make sure it is newer than version 1.0.

2. A Bokeh server is needed for full interactivity. Clone the repository. In the terminal, navigate to the directory, and then run:
```
bokeh serve project_Bokeh_mockdata.ipynb
```
Now, navigate to the following URL in a browser:
```
http://localhost:5006/project_Bokeh_mockdata
```
