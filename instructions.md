# [Iot][cloud] - Simulation of smart oxygen concentrator network


## The objective of this mini-project

The operating principle of an oxygen concentrator is very simple: the device sucks in the ambient air (composed of approximately 20% oxygen and 80% nitrogen), and makes it pass under high pressure by a filter which traps nitrogen molecules. This is a zeolite (a crystal) filter, and since a filter quickly saturates it needs cleaning.

A new concentrator produces 90-95% concentrated oxygen. But over time, a large number of saturation and cleaning cycles eventually deteriorate the filters, even if the unit has two.

Faced with COVID-19 Home oxygen therapy is imposed as the ultimate solution in order to shorten hospitalization, or even to avoid it for patients with severe COVID-19.

The objective of this work is to develop an application in the field of connected objects, which consists in simulating an intelligent network of oxygen concentrators, considering that each oxygen concentrator has 3 sensors: a position sensor, a sensor temperature sensor and an oxygen saturation sensor who transmit data to the cloud in a regular and adjustable interval for each device, in addition the device has a native sensors that send aditional informations : use time, oxygen_concentration and the device level set (level 1: only one filtre whos is working - level 2 both of filters are working).

The information transmitted by each device is ingested and classified to be subject to drastic monitoring of the patient's condition using the device as well as that of the device itself (integrated oxygen concentration capter). The second part of this job is to apply one of the machine learning algorithms and predict the ideal time to send a technician to change the filters on the device.

- ![How does oxygen concentrator work?] (https://summitoxygen.net/blog/how-does-oxygen-concentrator-work/)

## Prerequisites

- Python = 3.8.12
- Linux environment

## Pretreatment (1st part)

It is assumed that the data of all devices is collected in a log file [Log activities file](data/smart_oxygen_concentrator_activities.txt). This file contains an activity log of all devices as data in lines separated by -- Example: 02/01/21- 20:16:36 -- 2018 -- 131 -- 80 -- 95 -- 160 -- 1 -- 37 -- 90 
The goal of this step is to remove duplicate lines and generate a smart_oxygen_concentrator_data.csv file that will be used in predicting the ideal time to change device filters.
the expected file is in csv format (smart_oxygen_concentrator_data.csv) must contain the following columns corresponding to each element of the log file (smart_oxygen_concentrator_activities.log):

|device_id |x_position  | y_position |  oxygen_concentration | use_duration_in_min | level | temperature | patient_oxygen_saturation|                           
|:--------:|:----------:|:----------:|:---------------------:|:-------------------:|:-----:|:-----------:|:------------------------:|
| 2018     | 131        |  80        | 95                    | 160                 |  1    | 37          | 90                       |

## Prediction (2nd part)

Regarding the prediction part, the objective is to implement a predict () function which applies Bayesian regression to predict the ideal moment at which to perform a filter change intervention, **only for the device with id= 2018.

It is considered that a change of the filters of a device is necessary when oxygen concentration produced by the device is up to 80%.

Considering level and use_duration_in_min as input variables and device_oxygen_concentration as outputvariable

The result must be represented in the format of a graph. The example below that illustrates a Bayesian regression prediction graph of Bus waiting time between two stations:

 [Bayesian regression prediction graph](images/Figure_2.png) 


## Expected delivery 

- Python script for 1st part --> should have as result smart_oxygen_concentrator_data.csv file.

- Python script for Prediction 2nd part --> should have as input  smart_oxygen_concentrator_data.csv file and as output Bayesian regression graph.

## Reference

- [Machine Learning in Python] (https://scikit-learn.org/stable/)
- [Bayesian Regression] (https://scikit-learn.org/stable/modules/linear_model.html#bayesian-regression)




