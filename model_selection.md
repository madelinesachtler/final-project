# Potential Models

## Field Definitions

- Game Completed Date - Text string
    - Format: MM/DD/YYYY at H:MM:SS #m EST
    - This provides the exact time in EST that the game being played has finished, Win or Loss
- Team - Categorical
    - Options: Imposter, Crewmate
    - This provides the side or team that the user was a member of during this game which further determines the applicable metrics that we are allowed to track due to the different allowable actions for each team
- Outcome - Categorical
    - Options: Loss, Win
    - This provides the outcome of the game for that user
- Task Completed - Numeric
    - Range: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    - Only applicable to Crewmates, this describes the number of tasks completed by that user within the game
    - Each game, users are assigned a number of tasks that depend on two factors: the map being played on and the custom settings used
- All Tasks Completed - Categorical
    - Options: No, Yes
    - Dependent on Task Completed and only applicable to Crewmates, this describes if the user has completed all tasks assigned to them
    - The number of tasks necessary to achieve completeness will vary from game to game depending on two factors: the map being played on and the custom settings used
- Murdered - Categorical
    - Options: No, Yes
    - Only applicable to Crewmates, this describes if a user was murdered by a user opponent (Imposter) through the Kill action
    - This field and the Ejected field are mutually exclusive (you cannot be both Murdered and Ejected in the same game)
- Imposter Kills - Numeric
    - Range: [0, 1, 2, 3, 4, 5, 6, 7, 8]
    - Only applicable to Imposters, this describes the number of Crewmates that the user has murdered through the Kill action
    - The maximum number of kills that an Imposter can get in any one game is 8 because:
        - The maximum number of Crewmates allowed in any one game is 9
        - The minimum number of Imposters allowed in any one game is 1
        - The game will end in a Win Outcome for the Imposter side if the number of Imposters equals the number of Crewmates
- Game Length - Text string
    - Format: ##m ##s
    - This descrbes the length of the game in minutes and seconds in a non-datetime format
- Ejected - Categorical
    - Options: No, Yes
    - This describes if a user was murdered during the Voting process by the other players in the game
    - This field and the Murdered field are mutually exclusive (you cannot be both Murdered and Ejected in the same game)
- Sabotages Fixed - Numeric
    - Typical Range: [0, 1, 2, 3, 4, 5]
    - Only applicable to Crewmates, this field describes the number of Sabotages (actions performed by Imposters) that were resolved by the User
    - There are two major factors to influence the Typical Range:
        - There is no maximum number of sabotages that can be fixed but this will be limited to the number of Sabotages initiated and the length of the game itself
        - There are some Sabotages Fixed that can apply to two Users which can inflate this number on maps that these sabotages are more useful
- Time to complete all tasks - Text string
    - Format: ##m ##s
    - Dependent on All Tasks Completed and only applicable to Crewmates, this describes the time taken to complete all tasks and achieve a Yes for All Tasks Completed
    - Additionally, this field will is strictly less than Game Length
- Rank Change - Categorical
    - Options: -, --, ---, +, ++, +++
    - This field is largely vague but can loosely be described as the factor used in the matchmaking process, with:
        - -, --, --- are attributed to a Loss Outcome
        - +, ++, +++ are attributed to a Win Outcome
    - Large assumptions must be made to interpret the extent to which a field like ++ differs from +++ so we cannot use this field to make any appropriate conclusions
- Region/Game Code - Text string
    - Format: Region / GMECDE
    - This describes the region the server is in that the game is being played and the 6-character game code for the lobby the game is being played in
    - In most cases, there will be repeat Region/Game Codes as multiple games played in the same lobbies
    - In few cases, we will see multiple Users in the same lobbies playing in the same games
    - Lastly, this does not specify the location of each User as there is frequent Region hopping that wouldn't logistically be possible if the region specified matched the User location
- User - Categorical
    - Range: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29]
    - This is a field that we created for the explicit use in our project and analysis
    - There are 29 Users with varying numbers of games with a maximum of 100 games played
    - We created this field to distinguish which Users correspond to which records in order to account for bias in splitting our data between training and testing groups
- Time_of_Day - Categorical
    - Options: Night, Morning, Afternoon, Evening
    - This is a field that we created for the explicit use in our project and analysis
    - This field was created from time portion in the Game Completed Date field, binned in the following way:
        - Night: 12:00AM-5:59AM
        - Morning: 6:00AM-11:59AM
        - Afternoon: 12:00PM – 5:59PM
        - Evening: 6:00PM-11:59PM
    - We created this field to add another predictive field for Outcome as the time of the game that you're playing at may affect your ability to perform well in your role
- Date - Datetime
    - Format: MM/DD/YYYY
    - This is a field that we created for the explicit use in our project and analysis
    - This field was created from the date portion in the Game Completed Date field
    - We have yet to find an applicable use for this field

## Data Limitations
There are some limitations with the data that we have encountered that shape the scope of our analysis. The field descriptions were entirely created using the understanding of the game by the members of the project. In particular, the Rank Change field is a field that we do not feel confident in making conclusions with as we cannot define the scope of it's use and its implications.

We make an assumption that the games are being played in the Eastern Standard Time as a majority of Users play in both NA and Europe servers with a majority of those games being in NA. We imply that the data gathered was in North America with the most likely time zone being Eastern Standard Time as any other time zone would not lead to matchmaking with Europe servers. This is important so we can create the Time_of_Day field under the assumption that Game Completed Date is reflective of the local time.

Our Combined dataset is the result of combining 29 separate datasets for 29 separate Users. We have created a User field to keep track of which records belong to which User. This is so that we can maintain these pods when defining our training and testing groups. This makes it difficult to create evenly portioned training and testing groups for our Crewmate and Imposter analysis. However, we believe that it is more important to avoid bias by not training on records that we will later test on for that same User. We consider this a more explicit bias to be avoided.

## Data Transformations

Random Forest Classification: We will be using a Random Forest Classification model through the sklearn Python library in order to predict game outcomes for Imposter and Crewmate games. We will develop distinct models for making predictions for the two roles. We are doing this because there many exclusive fields for the roles such that we would have to exclude those fields otherwise. We will define all applicable fields that we will attempt to fit on for each model.

GridSearchCV: We use model_selection.GridSearchCV to hone in on the most appropriate parameters to pass into what we believe is our most accurate model. We will use the default number of folds (5) in order to determine the best choice for n_estimators and criterion in our Random Forest Classification Models. The possible options for n_estimators are: 10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 120, 130, 140, and 150. The possible options for criterion are gini and entropy which are different ways to measure the quality of the split.

Binary Encoding: In order to pass our data through to the Random Forest Classification model, we will have to convert all applicable categorical field. The is the data that you will see being displayed here. While in most cases we are able to convert to just one binary field, for the conversion of Time of Day we will have to have 4 separate fields to account for 4 possible options. Additionally, we have converted both the Game Length and Time to complete all tasks fields into numeric values in seconds. All numeric values are not encoded as they are already in an appropriate format. Here is the key for interpretting converted fields:

- Team
    - Imposter: 0
    - Crewmate: 1
- Outcome
    - Loss: 0
    - Win: 1
- All Tasks Completed
    - No: 0
    - Yes: 1
- Murdered
    - No: 0
    - Yes: 1
- Game Length
    - This is converted to numeric values in seconds
- Ejected - Categorical
    - No: 0
    - Yes: 1
- Time to complete all tasks - Text string
    - This is converted to numeric values in seconds
- Night
    - No: 0
    - Yes: 1
- Morning
    - No: 0
    - Yes: 1
- Afternoon
    - No: 0
    - Yes: 1
- Evening
    - No: 0
    - Yes: 1

Data Scaling: We will be scaling this data in the background prior to passing it our Random forest Classification models. We will not be transforming our binary fields. We will only scale our numeric fields including the newly altered Game Length and Time to complete all tasks fields. This will more appropriately standardize and scale our fields so that they don't have disproportionate weight when passed into our model.

## Imposter ML

Possible Features: Game Length, Imposter Kills, Ejected, Night, Morning, Afternoon, Evening

Model Features: Game Length, Imposter Kills, Ejected, Afternoon, Evening

After trial and error, we landed on these 5 features. For our Random Forest Classification model, we used model_selection.GridSearchCV in order to find the best parameters to pass into our model. These are our results and the importance of the individual features in predicting the Outcome of each game:

Score: 0.7
Parameters: n_estimators = 20, criterion = 'entropy'

## Crewmate ML

Possible Features: Game Length, Task Completed, All Tasks Completed, Sabotages Fixed, Murdered, Ejected, Night, Morning, Afternoon, Evening

Model Features: Game Length, Task Completed, Sabotages Fixed, Murdered, Ejected, Night, Morning, Afternoon, Evening

After trial and error, we landed on these 9 features. For our Random Forest Classification model, we used model_selection.GridSearchCV in order to find the best parameters to pass into our model. These are our results and the importance of the individual features in predicting the Outcome of each game:

Score: 0.6150627615062761
Parameters: n_estimators = 50, criterion = 'entropy'

## Imposter

### Writeup

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
- RFC - 0.7
    - Order of Importance:
        - (0.6796233699639577, 'Game Length')
        - (0.15952139066979176, 'Ejected')
        - (0.11394373072584152, 'Imposter Kills')
        - (0.024481463572779617, 'Evening')
        - (0.022430045067629436, 'Afternoon')

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
- RFC - 0.6150627615062761
    - Order of Importance:
        - (0.6445397581683949, 'Game Length')
        - (0.14356417238613303, 'Task Completed')
        - (0.06576053015844335, 'Sabotages Fixed')
        - (0.054699844790526156, 'Murdered')
        - (0.017843036041224773, 'All Tasks Completed')
        - (0.016914637865102784, 'Evening')
        - (0.016548463795283033, 'Ejected')
        - (0.014369827485476891, 'Afternoon')
        - (0.01382214761103475, 'Night')
        - (0.011937581698380354, 'Morning')
        
### Model 2
- Fields: "Game Length", "Task Completed", "All Tasks Completed", "Sabotages Fixed", "Murdered", "Ejected", "Morning", "Afternoon", "Evening"
- DTC - 0.5774058577405857
    - Order of Importance:
        - (0.5846131684876373, 'Game Length')
        - (0.1195015298762009, 'Task Completed')
        - (0.08025546751934998, 'Sabotages Fixed')
        - (0.04917092064269182, 'Evening')
        - (0.0435941946884785, 'Murdered')
        - (0.040678510116754156, 'Afternoon')
        - (0.036250016443095855, 'Morning')
        - (0.029938234863497164, 'All Tasks Completed')
        - (0.015997957362294292, 'Ejected')
- RFC - 0.6276150627615062
    - Order of Importance:
        - (0.6407048344322205, 'Game Length')
        - (0.1430348589732038, 'Task Completed')
        - (0.06549073543690553, 'Sabotages Fixed')
        - (0.05035684521982558, 'Murdered')
        - (0.025549034086443927, 'Evening')
        - (0.02292309722094385, 'Afternoon')
        - (0.018143558544316696, 'Ejected')
        - (0.01786035799797627, 'All Tasks Completed')
        - (0.01593667808816386, 'Morning')

### Model 3
- Fields: "Game Length", "Task Completed", "Sabotages Fixed", "Murdered", "Ejected", "Morning", "Afternoon", "Evening"
- DTC - 0.602510460251046
    - Order of Importance:
        - (0.6145579376866471, 'Game Length')
        - (0.1263992215986235, 'Task Completed')
        - (0.08876481658981691, 'Sabotages Fixed')
        - (0.043594194688478506, 'Murdered')
        - (0.04187269704732493, 'Evening')
        - (0.0392475682264252, 'Afternoon')
        - (0.029565606800389624, 'Morning')
        - (0.015997957362294295, 'Ejected')
- RFC - 0.5815899581589958
    - Order of Importance:
        - (0.672948813957116, 'Game Length')
        - (0.14915040933519644, 'Task Completed')
        - (0.0636539418922138, 'Sabotages Fixed')
        - (0.054068020768294846, 'Murdered')
        - (0.01689915884424858, 'Ejected')
        - (0.0165840804127642, 'Evening')
        - (0.015645376546108824, 'Afternoon')
        - (0.0110501982440573, 'Morning')
        
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
        - (0.6722059253253261, 'Game Length')
        - (0.1411638726266161, 'Task Completed')
        - (0.06751888008754144, 'Sabotages Fixed')
        - (0.053912778074309976, 'Murdered')
        - (0.01857189786410841, 'Evening')
        - (0.017718216440317763, 'Afternoon')
        - (0.015514575905034614, 'All Tasks Completed')
        - (0.013393853676745475, 'Morning')
        
### Model 5
- Fields: "Game Length", "Task Completed", "Sabotages Fixed", "Murdered", "Ejected", "Night", "Morning", "Afternoon", "Evening"
- DTC - 0.5355648535564853
    - Order of Importance:
        - (0.6014750378444914, 'Game Length')
        - (0.12360354458074953, 'Task Completed')
        - (0.08100071111643435, 'Sabotages Fixed')
        - (0.044880414545508805, 'Evening')
        - (0.04359419468847852, 'Murdered')
        - (0.04172718971304592, 'Afternoon')
        - (0.03611613032044552, 'Morning')
        - (0.02760277719084596, 'All Tasks Completed')
- RFC - 0.5941422594142259
    - Order of Importance:
        - (0.6722059253253261, 'Game Length')
        - (0.1411638726266161, 'Task Completed')
        - (0.06751888008754144, 'Sabotages Fixed')
        - (0.053912778074309976, 'Murdered')
        - (0.01857189786410841, 'Evening')
        - (0.017718216440317763, 'Afternoon')
        - (0.015514575905034614, 'All Tasks Completed')
        - (0.013393853676745475, 'Morning')