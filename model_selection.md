# Potential Models

## Imposter

### All Fields
"Game Length", "Imposter Kills", "Ejected", "Night", "Morning", "Afternoon", "Evening"

### Model 1 
- Fields: "Game Length", "Imposter Kills", "Ejected", "Night", "Morning", "Afternoon", "Evening"
- DTC - 0.6428571428571429
    - Order of Importance:
        - (0.6077808620934279, 'Game Length')
        - (0.18313495173502667, 'Ejected')
        - (0.11753200699568495, 'Imposter Kills')
        - (0.0327158563880437, 'Afternoon')
        - (0.023444401000083485, 'Evening')
        - (0.02232557970206204, 'Morning')
        - (0.01306634208567141, 'Night')
- RFC - 0.6714285714285714
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
- DTC - 0.5571428571428572
    - Order of Importance:
        - (0.7123858043026532, 'Game Length')
        - (0.18697918395803603, 'Ejected')
        - (0.10063501173931079, 'Imposter Kills')
- RFC - 0.5714285714285714
    - Order of Importance:
        - (0.7257980196773609, 'Game Length')
        - (0.1848321851650571, 'Ejected')
        - (0.08936979515758196, 'Imposter Kills')
        
### Model 3
- Fields: "Game Length", "Imposter Kills", "Ejected", "Night", "Evening"
- DTC - 0.6
    - Order of Importance:
        - (0.6321958811676404, 'Game Length')
        - (0.18313495173502667, 'Ejected')
        - (0.09693212318504882, 'Imposter Kills')
        - (0.05925094168954822, 'Evening')
        - (0.028486102222735947, 'Night')
- RFC - 0.6714285714285714
    - Order of Importance:
        - (0.6559329342776339, 'Game Length')
        - (0.1793411972824306, 'Ejected')
        - (0.11735652182921855, 'Imposter Kills')
        - (0.02600410109924869, 'Evening')
        - (0.021365245511468216, 'Night')

### Model 4
- Fields: "Game Length", "Imposter Kills", "Ejected", "Afternoon", "Evening"
- DTC - 0.6428571428571429
    - Order of Importance:
        - (0.6234192245761346, 'Game Length')
        - (0.1840811139426129, 'Ejected')
        - (0.11327490065910534, 'Imposter Kills')
        - (0.042864424494734495, 'Afternoon')
        - (0.03636033632741271, 'Evening')
- RFC - 0.7142857142857143
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
- DTC - 0.5690376569037657
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
- RFC - 0.606694560669456
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
- Fields: "Game Length", "Task Completed", "All Tasks Completed", "Sabotages Fixed", "Murdered", "Ejected", "Morning", "Afternoon", "Evening"
- DTC - 0.5857740585774058
    - Order of Importance:
        - (0.5827661119333605, 'Game Length')
        - (0.11954121878687157, 'Task Completed')
        - (0.07848907209998987, 'Sabotages Fixed')
        - (0.04791989570205005, 'Evening')
        - (0.04682401181758376, 'Afternoon')
        - (0.043594194688478506, 'Murdered')
        - (0.036509695830830545, 'Morning')
        - (0.028357841778540987, 'All Tasks Completed')
        - (0.015997957362294295, 'Ejected')
- RFC - 0.5983263598326359
    - Order of Importance:
        - (0.6419366875190505, 'Game Length')
        - (0.1409275775346765, 'Task Completed')
        - (0.06671022729461266, 'Sabotages Fixed')
        - (0.05285837650583174, 'Murdered')
        - (0.023834122454847652, 'Evening')
        - (0.021125124389244, 'Afternoon')
        - (0.018839416225939494, 'All Tasks Completed')
        - (0.017689236608504084, 'Ejected')
        - (0.016079231467293453, 'Morning')

### Model 3
- Fields: "Game Length", "Task Completed", "Sabotages Fixed", "Murdered", "Ejected", "Morning", "Afternoon", "Evening"
- DTC - 0.5941422594142259
    - Order of Importance:
        - (0.5990158950383506, 'Game Length')
        - (0.13284874888803555, 'Task Completed')
        - (0.08744959012985341, 'Sabotages Fixed')
        - (0.04542488992225393, 'Afternoon')
        - (0.04359419468847851, 'Murdered')
        - (0.04220786766131564, 'Evening')
        - (0.03346085630941799, 'Morning')
        - (0.0159979573622943, 'Ejected')
- RFC - 0.6108786610878661
    - Order of Importance:
        - (0.6681262553988455, 'Game Length')
        - (0.15455103394050293, 'Task Completed')
        - (0.06091332188137887, 'Sabotages Fixed')
        - (0.05639939515449684, 'Murdered')
        - (0.01669143523092828, 'Ejected')
        - (0.01588573584503416, 'Afternoon')
        - (0.015099666345207955, 'Evening')
        - (0.012333156203605576, 'Morning')
        
### Model 4
- Fields: "Game Length", "Task Completed", "All Tasks Completed", "Sabotages Fixed", "Murdered", "Morning", "Afternoon", "Evening"
- DTC - 0.5397489539748954
    - Order of Importance:
        - (0.6115818279995003, 'Game Length')
        - (0.11358898149229184, 'Task Completed')
        - (0.08264910344016498, 'Sabotages Fixed')
        - (0.04848827164515879, 'Evening')
        - (0.043594194688478534, 'Murdered')
        - (0.03872974618412904, 'Afternoon')
        - (0.032457045996378615, 'Morning')
        - (0.02891082855389793, 'All Tasks Completed')
- RFC - 0.5815899581589958
    - Order of Importance:
        - (0.6772647201919592, 'Game Length')
        - (0.14129626258909206, 'Task Completed')
        - (0.06615173174178486, 'Sabotages Fixed')
        - (0.049748490360219846, 'Murdered')
        - (0.019660307072998644, 'Evening')
        - (0.017685456397077123, 'Afternoon')
        - (0.015053153290260251, 'All Tasks Completed')
        - (0.013139878356608035, 'Morning')
        
### Model 5
- Fields: "Game Length", "Task Completed", "Sabotages Fixed", "Murdered", "Ejected", "Night", "Morning", "Afternoon", "Evening"
- DTC - 0.5481171548117155
    - Order of Importance:
        - (0.5972112871391243, 'Game Length')
        - (0.12618136856826237, 'Task Completed')
        - (0.08916343187686591, 'Sabotages Fixed')
        - (0.043594194688478506, 'Murdered')
        - (0.03827696132728934, 'Evening')
        - (0.03637831434011873, 'Morning')
        - (0.030185278154165985, 'Afternoon')
        - (0.023011206543400615, 'Night')
        - (0.015997957362294295, 'Ejected')
- RFC - 0.6317991631799164
    - Order of Importance:
        - (0.6608181759835491, 'Game Length')
        - (0.15673425673302535, 'Task Completed')
        - (0.06697509022463712, 'Sabotages Fixed')
        - (0.04952074353139898, 'Murdered')
        - (0.017901295171507285, 'Ejected')
        - (0.014533000781459322, 'Evening')
        - (0.011898392376413405, 'Afternoon')
        - (0.011762853326605534, 'Night')
        - (0.009856191871403915, 'Morning')