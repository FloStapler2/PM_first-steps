# Process_Mining_first-steps
Synthetic data generation using Python package [Faker](https://faker.readthedocs.io/en/master/), event-log generation with Python and initial analysis using Opensource-Tool [ProM](https://promtools.org/).

### Problem:
During the implementation of a process mining project in a manufacturing German company, it was unfortunately not possible to obtain real process data. 
### Solution: 
To solve the problem and to gain first experiences with process mining, synthetic data was generated. Data of a logistic process should be created.
The article [*'Process Mining in 5 Schritten'*](https://www.informatik-aktuell.de/betrieb/kuenstliche-intelligenz/process-mining-in-5-schritten.html) was used as an example to generate the logistics data. 

## Procedure:
1. Creating three data sources. These are combined into one data table based on their foreign key relationships. The following code is used for this: [Faker_data_generator.ipynb](Faker_data_generator.ipynb) <br>
The data sources come from three different systems:
   1. **Warehouse-Management-System:** Movements in the WMS &rarr; **Result:** [synthetic_WMS_data.csv](created_files/datatables/synthetic_WMS_data.csv)
   2. **Picking-System:** Picking information &rarr; **Result:** [synthetic_VER_data.csv](created_files/datatables/synthetic_VER_data.csv)
   3. **Shipping-System:** Shipping information &rarr; **Result:** [synthetic_KOM_data.csv](created_files/datatables/synthetic_KOM_data.csv)
   4. **Merged data source:** Including all information from 1, 2 & 3 &rarr; **Result:** [synthetic_merged_data.csv](synthetic_merged_data.csv)
      
2. Using the [synthetic_merged_data.csv](synthetic_merged_data.csv) as input for [event-log_creator.ipynb](event-log_creator.ipynb), to create a Event-log. An event log was created which uses all information from the available data sets. Furthermore, an edited event log was created, which only contains entries for further use. <br>
   1. **Event-log:** Contains all informations from the provided datasets &rarr; **Result:** [event-log.csv](event-log.csv)
   2. **Short Event-log:** Contains only time-related informations &rarr; **Result:** [event-log_short.csv](event-log_short.csv)
  
3. Using ProM for analysis
   1. Create an xes file with the ...-Plugin
   2. Create a ...tree
   3. Discovery
   4. performance 

## Useful links:
* Faker documentation: [here](https://faker.readthedocs.io/en/master/)
* ProM tool: [here](https://promtools.org/)


