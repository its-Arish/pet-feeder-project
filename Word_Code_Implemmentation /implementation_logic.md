START SYSTEM
//The Main process begins to run in an endless loop
LOOP forever:
  //  Module 1 Check feed time 
    READ currentTime
    IF currentTime == feedingTime1 OR currentTime == feedingTime2 THEN
  //Module 2: Check on the food hopper status, hence we will call checkHopper function
        CALL checkHopper()
  //  Module 3: This role will feed the food
        CALL dispenseFood()
   //  Module 4: Track Pet consumption 
        CALL monitorEating()

    ENDIF

END LOOP

FUNCTION checkHopper():
    IF hopperEmpty == TRUE THEN
        alertType = "HOPPER_EMPTY"
        activateAlert = TRUE
        STOP cycle
    ENDIF
END FUNCTION

FUNCTION dispenseFood():
    activateMotor = TRUE
    DISPENSE until bowlWeight increases by dispenseAmount
    activateMotor = FALSE
END FUNCTION

FUNCTION monitorEating():
    WAIT 30 mins
    IF bowlWeight has gone down THEN
        //In case pet has eaten
        GO BACK to main loop
    ELSE
       // In case pet does not eat
        alertType = "NOT_EATEN"
        activateAlert = TRUE
        STOP cycle
    ENDIF
END FUNCTION
