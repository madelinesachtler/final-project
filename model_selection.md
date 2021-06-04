# Potential Models

## Imposter

### All Fields
"Game Length", "Imposter Kills", "Ejected", "Night", "Morning", "Afternoon", "Evening"

### Model 1 
- Fields: "Game Length", "Imposter Kills", "Ejected", "Night", "Morning", "Afternoon", "Evening"
- DTC - 0.7285714285714285
    - Order of Importance:
        - (0.6077808620934279, 'Game Length')
        - (0.18313495173502667, 'Ejected')
        - (0.11753200699568495, 'Imposter Kills')
        - (0.0327158563880437, 'Afternoon')
        - (0.023444401000083485, 'Evening')
        - (0.02232557970206204, 'Morning')
        - (0.01306634208567141, 'Night')
- RFC - 0.8142857142857143
    - Order of Importance:
        - (0.646790528064293, 'Game Length')
        - (0.18130321214056458, 'Ejected')
        - (0.11693955321110565, 'Imposter Kills')
        - (0.01558925325201164, 'Night')
        - (0.01460442146592011, 'Evening')
        - (0.013620398689973489, 'Morning')
        - (0.011152633176131563, 'Afternoon')
    
### Model 2
- Fields: "Game Length", "Imposter Kills", "Ejected"
- DTC - 0.7142857142857143
    - Order of Importance:
        - (0.7123858043026532, 'Game Length')
        - (0.18697918395803603, 'Ejected')
        - (0.10063501173931079, 'Imposter Kills')
- RFC - 0.7857142857142857
    - Order of Importance:
        - (0.7257980196773609, 'Game Length')
        - (0.1848321851650571, 'Ejected')
        - (0.08936979515758196, 'Imposter Kills')
        
### Model 3
- Fields: "Game Length", "Imposter Kills", "Ejected", "Night", "Evening"
- DTC - 0.7714285714285715
    - Order of Importance:
        - (0.6321958811676404, 'Game Length')
        - (0.18313495173502667, 'Ejected')
        - (0.09693212318504882, 'Imposter Kills')
        - (0.05925094168954822, 'Evening')
        - (0.028486102222735947, 'Night')
- RFC - 0.8
    - Order of Importance:
        - (0.6559329342776339, 'Game Length')
        - (0.1793411972824306, 'Ejected')
        - (0.11735652182921855, 'Imposter Kills')
        - (0.02600410109924869, 'Evening')
        - (0.021365245511468216, 'Night')

### Model 4
- Fields: "Game Length", "Imposter Kills", "Ejected", "Afternoon", "Evening"
- DTC - 0.8
    - Order of Importance:
        - (0.6234192245761346, 'Game Length')
        - (0.1840811139426129, 'Ejected')
        - (0.11327490065910534, 'Imposter Kills')
        - (0.042864424494734495, 'Afternoon')
        - (0.03636033632741271, 'Evening')
- RFC - 0.8428571428571429
    - Order of Importance:
        - (0.6503956911608282, 'Game Length')
        - (0.1949863238433754, 'Ejected')
        - (0.10894650715329693, 'Imposter Kills')
        - (0.023608592825611598, 'Evening')
        - (0.02206288501688808, 'Afternoon')

## Crewmate
"Game Length", "Task Completed", "All Tasks Completed", "Time to complete all tasks", "Sabotages Fixed", "Murdered", "Ejected", "Night", "Morning", "Afternoon", "Evening'  
*Time to complete all tasks* will only be considered for a subsection such that *All Tasks Completed* = 1  

### Model 1
- Fields: "Game Length", "Task Completed", "All Tasks Completed", "Sabotages Fixed", "Murdered", "Ejected", "Night", "Morning", "Afternoon", "Evening"
- DTC - 0.5732217573221757
    - Order of Importance:
        - (0.5884432617061653, 'Game Length')
        - (0.11407090809788384, 'Task Completed')
        - (0.07550651906445927, 'Sabotages Fixed')
        - (0.04359419468847851, 'Murdered')
        - (0.03856743764248584, 'Evening')
        - (0.03843242531634015, 'Morning')
        - (0.03544730293889921, 'Afternoon')
        - (0.0312608859889605, 'All Tasks Completed')
        - (0.018679107194033085, 'Night')
        - (0.0159979573622943, 'Ejected')
- RFC - 0.6108786610878661
    - Order of Importance:
        - (0.6466626177577435, 'Game Length')
        - (0.1387208660265315, 'Task Completed')
        - (0.06908506309409737, 'Sabotages Fixed')
        - (0.05138654638041172, 'Murdered')
        - (0.017307958071834564, 'Afternoon')
        - (0.017299178075390192, 'Evening')
        - (0.01652204560768987, 'Ejected')
        - (0.01643801836666229, 'All Tasks Completed')
        - (0.014894131014961, 'Night')
        - (0.01168357560467807, 'Morning')
        
### Model 2
- Fields: "Game Length", "Task Completed", "All Tasks Completed", "Sabotages Fixed", "Murdered", "Ejected", "Afternoon", "Evening"
- DTC - 0.5983263598326359
    - Order of Importance:
        - (0.601510686608593, 'Game Length')
        - (0.1337507530905525, 'Task Completed')
        - (0.07991849685737691, 'Sabotages Fixed')
        - (0.052544917924572936, 'Evening')
        - (0.0436525336714097, 'Murdered')
        - (0.042383647423083155, 'Afternoon')
        - (0.030219598143609836, 'All Tasks Completed')
        - (0.016019366280801958, 'Ejected')
- RFC - 0.6401673640167364
    - Order of Importance:
        - (0.6648172991934164, 'Game Length')
        - (0.14012856693462653, 'Task Completed')
        - (0.06558586762623962, 'Sabotages Fixed')
        - (0.05575811960314583, 'Murdered')
        - (0.022179778026281877, 'Evening')
        - (0.019626429308095886, 'Afternoon')
        - (0.016173012687398628, 'Ejected')
        - (0.01573092662079528, 'All Tasks Completed')
        
### Model 3
- Fields: "Game Length", "Task Completed", "Sabotages Fixed", "Murdered", "Ejected", "Afternoon", "Evening"
- DTC - 0.5732217573221757
    - Order of Importance:
        - (0.6213996450790329, 'Game Length')
        - (0.13887700471566372, 'Task Completed')
        - (0.08586025692334874, 'Sabotages Fixed')
        - (0.04985956725123245, 'Afternoon')
        - (0.04433162607851048, 'Evening')
        - (0.0436525336714097, 'Murdered')
        - (0.016019366280801958, 'Ejected')
- RFC - 0.602510460251046
    - Order of Importance:
        - (0.6881697946344802, 'Game Length')
        - (0.1505120824376232, 'Task Completed')
        - (0.06007554985853608, 'Sabotages Fixed')
        - (0.052420667758353585, 'Murdered')
        - (0.017470746534834717, 'Evening')
        - (0.015857841305888246, 'Ejected')
        - (0.015493317470283666, 'Afternoon')
        
### Model 4
- Fields: "Game Length", "Task Completed", "All Tasks Completed", "Sabotages Fixed", "Murdered", "Afternoon", "Evening"
- DTC - 0.5732217573221757
    - Order of Importance:
        - (0.6294867587710634, 'Game Length')
        - (0.12559133225060756, 'Task Completed')
        - (0.08476195096559361, 'Sabotages Fixed')
        - (0.04571683905724873, 'Afternoon')
        - (0.044760410835598535, 'Evening')
        - (0.04365253367140969, 'Murdered')
        - (0.026030174448478296, 'All Tasks Completed')
- RFC - 0.5815899581589958
    - Order of Importance:
        - (0.6877863388219295, 'Game Length')
        - (0.1393387748008451, 'Task Completed')
        - (0.06332193988212506, 'Sabotages Fixed')
        - (0.05255520837684824, 'Murdered')
        - (0.021329750499614504, 'Evening')
        - (0.019373946291135518, 'Afternoon')
        - (0.016294041327502062, 'All Tasks Completed')
        
### Model 5
- Fields: "Game Length", "Task Completed", "All Tasks Completed", "Sabotages Fixed", "Murdered", "Ejected", "Evening"
- DTC - 0.5606694560669456
    - Order of Importance:
        - (0.6103302260250512, 'Game Length')
        - (0.14319467450990525, 'Task Completed')
        - (0.08715599813601535, 'Sabotages Fixed')
        - (0.06517440498009291, 'Evening')
        - (0.043926859773559056, 'Murdered')
        - (0.03409779961314728, 'All Tasks Completed')
        - (0.016120036962228943, 'Ejected')
- RFC - 0.602510460251046
    - Order of Importance:
        - (0.7086152228607536, 'Game Length')
        - (0.12457892275976691, 'Task Completed')
        - (0.057810387507317894, 'Sabotages Fixed')
        - (0.049308026149480155, 'Murdered')
        - (0.026400358957151683, 'Evening')
        - (0.01767774818002879, 'Ejected')
        - (0.015609333585500982, 'All Tasks Completed')