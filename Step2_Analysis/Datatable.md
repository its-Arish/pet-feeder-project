## Organise and Describe the Data

This step entails making a list of all the data that the system will access such as the inputs by sensors, as well as, outputs to control hardware. The table below details each data point, its purpose, and sample values, as required.

| Variables             | Data type | Input/Output | Format                           |
| :-------------------- | :-------- | :----------- | :------------------------------- |
| currentTime           | Time      | Input        | "08:10, 19:00"                   |
| foodlevelSensorStatus | boolean   | Input        | True or False                    |
| BowlWeight            | Discrete  | Input        | 50 (grams)                       |
| feedingTime1          | Time      | Input        | 00:00                            |
| feedingTime2          | Time      | Input        | 01:00                            |
| dispenseAmount        | Discrete  | Output       | 100(grams)                       |
| activateMotor         | Boolean   | Output       | True or False                    |
| activateAlert         | Boolean   | Output       | True or False                    |
| alertType             | String    | Output       | “Low_food_level” , “ NOT_Eaten” |
