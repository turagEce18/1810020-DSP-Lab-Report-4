## **Roll: 1810020**
## **Course Code: ECE 4124**

### **<u>Experiment No:</u> 04**

### **<u>Experiment Date:</u> 15.05.2023**

### **<u>Experiment Name:</u> Study of Time Delay of a Signal Using the Cross-correlation Method** 

<br>


### **<u>Theory:</u>**
                 
<br>                 
    The lab experiment involves studying the time delay of a signal and analyzing its cross-correlation with the original signal. Time delay refers to a shift in the timing of a signal, and cross-correlation measures the similarity between two signals at different time lags. By applying different time delays and calculating cross-correlation, we gain insights into signal alignment and similarity. This analysis is useful in signal processing, communication systems, and pattern recognition applications. 

<br><br>
            



### **<u>Code:</u>**
<br>

```clc 
clear all 
t=0:0.1:40 
x1=(t>=0 & t<=10); 
x2=(t>=10 & t<=15); 
x3=(t>=15 & t<=25); 
x4=(t>=25 & t<=40); 
signal1 = 1*x1+0*x2-1*x3+0*x4; 
subplot(3,1,1); 
plot(t,signal1); 
title('Main Signal'); 
delay = 5; 
x5=(t>=0+delay & t<=10+delay); 
x6=(t>=10+delay & t<=15+delay); 
x7=(t>=15+delay & t<=25+delay); 
x8=(t>=25+delay & t<=40+delay); 
signal2 = 1*x5+0*x6-1*x7+0*x8; 
subplot(3,1,2); 
plot(t,signal2); 
title('Delay Signal'); 
signal3 = xcorr(signal1,signal2); 
subplot(3,1,3); 
plot(signal3); 
xlim([0 800]); 
title('Cross-correlation of signals'); 
[~, max_index] = max(signal3); 
delay_time =(length(signal1)-max_index); 
disp('Delay Time: '); 
disp(delay_time*0.1);
```


<br><br>



### **<u>Output:</u>** 
<br>

<div align="center">
<img src="./output.png" alt="Figure-1: Cross-correlation of Delayed Signal Output">
<br>
<h4> Figure-1: Cross-correlation of Delayed Signal Output </h4> 
</div>


<br><br>


### **<u>Discussion:</u>** 
<br>
The lab experiment focused on studying time delay and cross-correlation of a signal. We observed how different time delays affected the similarity between the original signal and its delayed versions using cross-correlation analysis. As the time delay increased, the cross-correlation decreased, indicating reduced alignment and similarity between the signals. 

<br><br>

### **<u>Conclusion:</u>**
<br> 
The experiment highlighted the significance of time alignment and its impact on signal similarity. By analyzing cross-correlation, we gained insights into the relationship between time delay and signal correlation. This knowledge has practical applications in signal processing, communication systems, and pattern recognition, providing valuable insights for tasks such as time delay estimation and signal synchronization.

