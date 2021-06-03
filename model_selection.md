# Potential Models

## Imposter

### All Fields
"Game Length", "Imposter Kills", "Ejected", "Night", "Morning", "Afternoon", "Evening"

### Model 1 
- Fields: "Game Length", "Imposter Kills", "Ejected", "Night", "Morning", "Afternoon", "Evening"
- RTC - 0.7285714285714285
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
- RTC - 0.7142857142857143
    - Order of Importance:
        - (0.715209627709567, 'Game Length')
        - (0.18697918395803603, 'Ejected')
        - (0.097811188332397, 'Imposter Kills')
- RFC - 0.7857142857142857
    - Order of Importance:
        - (0.7311308795676691, 'Game Length')
        - (0.18170925426625548, 'Ejected')
        - (0.08715986616607543, 'Imposter Kills')
        
### Model 3
- Fields: "Game Length", "Imposter Kills", "Ejected", "Night", "Evening"
- RTC - 0.7714285714285715
    - Order of Importance:
        - (0.6035836595799762, 'Game Length')
        - (0.18313495173502667, 'Ejected')
        - (0.10035873654884093, 'Imposter Kills')
        - (0.07809731519040489, 'Evening')
        - (0.03482533694575137, 'Night')
- RFC - 0.8142857142857143
    - Order of Importance:
        - (0.65293048694472, 'Game Length')
        - (0.18172437680988576, 'Ejected')
        - (0.11424796874157617, 'Imposter Kills')
        - (0.02715773793910762, 'Evening')
        - (0.023939429564710492, 'Night')

### Model 4
- Fields: "Game Length", "Imposter Kills", "Ejected", "Afternoon", "Evening"
- RTC - 0.7714285714285715
    - Order of Importance:
        - (0.6181256375661297, 'Game Length')
        - (0.18408111394261287, 'Ejected')
        - (0.11110580110194608, 'Imposter Kills')
        - (0.043633143887246685, 'Afternoon')
        - (0.0430543035020647, 'Evening')
- RFC - 0.8428571428571429
    - Order of Importance:
        - (0.6564780047658015, 'Game Length')
        - (0.182189843519634, 'Ejected')
        - (0.11533834457199822, 'Imposter Kills')
        - (0.023685677635823556, 'Evening')
        - (0.02230812950674277, 'Afternoon')

## Crewmate
"Game Length", "Task Completed", "All Tasks Completed", "Time to complete all tasks", "Sabotages Fixed", "Murdered", "Ejected", "Night", "Morning", "Afternoon", "Evening'  
*Time to complete all tasks* will only be considered for a subsection such that *All Tasks Completed* = 1  

### Model 1
- Fields: "Game Length", "All Tasks Completed", "Sabotages Fixed", "Murdered", "Ejected", "Night", "Morning", "Afternoon", "Evening"
- RTC - 0.5523012552301255
    - Order of Importance:
        - (0.6695162492787492, 'Game Length')
        - (0.0750509640246333, 'Sabotages Fixed')
        - (0.046093537811399014, 'Evening')
        - (0.04434487526170046, 'Murdered')
        - (0.04358953321429925, 'Morning')
        - (0.03895399157005483, 'All Tasks Completed')
        - (0.03789857752938952, 'Afternoon')
        - (0.02827883332697718, 'Night')
        - (0.016273437982797224, 'Ejected')
- RFC - 0.5732217573221757
    - Order of Importance:
        - (0.8006632718133853, 'Game Length')
        - (0.06274241071011818, 'Sabotages Fixed')
        - (0.053290617455016856, 'Murdered')
        - (0.022130291229286968, 'All Tasks Completed')
        - (0.018765804060689232, 'Ejected')
        - (0.01194482215242121, 'Evening')
        - (0.01165698067129593, 'Afternoon')
        - (0.010382224457583489, 'Night')
        - (0.008423577450202776, 'Morning')
        
### Model 2
- Fields: "Game Length", "All Tasks Completed", "Sabotages Fixed", "Murdered", "Ejected", "Morning", "Evening"
- RTC - 0.5564853556485355
    - Order of Importance:
        - (0.6989805411635828, 'Game Length')
        - (0.09350603161491522, 'Sabotages Fixed')
        - (0.06438180323954798, 'Evening')
        - (0.04483245617359656, 'Murdered')
        - (0.04366401804001136, 'Morning')
        - (0.038182782029077475, 'All Tasks Completed')
        - (0.016452367739268763, 'Ejected')
- RFC - 0.5732217573221757
    - Order of Importance:
        - (0.8279420192037262, 'Game Length')
        - (0.05356048026560624, 'Murdered')
        - (0.05285730396384735, 'Sabotages Fixed')
        - (0.019212973480217076, 'All Tasks Completed')
        - (0.01813028286602359, 'Evening')
        - (0.017682557025262446, 'Ejected')
        - (0.010614383195316962, 'Morning')
        
### Model 3
- Fields: "Game Length", "All Tasks Completed", "Sabotages Fixed", "Murdered", "Ejected"
- RTC - 0.5355648535564853
    - Order of Importance:
        - (0.7931392660050682, 'Game Length')
        - (0.09940654572757314, 'Sabotages Fixed')
        - (0.047182081737557044, 'Murdered')
        - (0.04295748614753272, 'All Tasks Completed')
        - (0.017314620382268747, 'Ejected')
- RFC - 0.5313807531380753
    - Order of Importance:
        - (0.876628398091133, 'Game Length')
        - (0.0503820319042519, 'Murdered')
        - (0.038320313617043196, 'Sabotages Fixed')
        - (0.018990816647891817, 'Ejected')
        - (0.01567843973968014, 'All Tasks Completed')
        
### Model 4
- Fields: "Game Length", "All Tasks Completed", "Sabotages Fixed", "Murdered", "Ejected", "Evening"
- RTC - 0.5690376569037657
    - Order of Importance:
        - (0.7419477857073844, 'Game Length')
        - (0.08518079582710646, 'Sabotages Fixed')
        - (0.07079979209175634, 'Evening')
        - (0.045599137181833484, 'Murdered')
        - (0.03973876908066845, 'All Tasks Completed')
        - (0.016733720111250915, 'Ejected')
- RFC - 0.5815899581589958
    - Order of Importance:
        - (0.8378830573779362, 'Game Length')
        - (0.052885986264485325, 'Murdered')
        - (0.04999305954487752, 'Sabotages Fixed')
        - (0.020706149317058338, 'Evening')
        - (0.02021472476999123, 'All Tasks Completed')
        - (0.01831702272565135, 'Ejected')
        
### Model 5
- Fields: "Game Length", "All Tasks Completed", "Sabotages Fixed", "Murdered", "Evening"
- RTC - 0.5606694560669456
    - Order of Importance:
        - (0.74447207058485, 'Game Length')
        - (0.09219444102280017, 'Sabotages Fixed')
        - (0.07027560802114202, 'Evening')
        - (0.047330899325364564, 'All Tasks Completed')
        - (0.045726981045843156, 'Murdered')
- RFC - 0.5732217573221757
    - Order of Importance:
        - (0.8627379135792111, 'Game Length')
        - (0.048672939769021414, 'Sabotages Fixed')
        - (0.04823418500271146, 'Murdered')
        - (0.02194502441754402, 'Evening')
        - (0.018409937231512005, 'All Tasks Completed')