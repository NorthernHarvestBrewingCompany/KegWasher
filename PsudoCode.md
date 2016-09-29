'''cpp
bool  Cleaning_Vessel_Heater(var SET_POINT)
        while(Water Level is > Minumum Water Level)
        {
          PID Controller(var SET_POINT)
        }

void  PID(SET_POINT)
    {
      /****PID TEMPRARURE CONTROL FUNCTION HERE *****/
    }

bool Get_Valve_State(int VALVE_ID)
{
  if(GPIO.input(VALVE_ID)){return TRUE;}
  return FALSE;
}

bool Change_Valve(bool STATE, int VALVE_ID)
{ //TRUE=OPEN -- FALSE=CLOSED
  
  //Check if there is a state change
  if(STATE == Get_Valve_State(VALVE_ID))
  {
    //State = Current State of Valve, No Change
    return TRUE;
  }
  
  //Valve Needs a State Change
  //IF Set_Valve Returns TRUE == Sucess
  else if (Set_Valve(STATE))
  {
    return TRUE;
  }
  
  //Somthing didn't work, Abort and stop
  return FALSE;
}


_____________________________________________________________
/** Main Function **/

int main()
{
  //Default Cleaner Temp to 150 * F

  double Cleaner_Temp = 150;
  std::cin >> Cleaner_Temp; 

  //Initialize System:
  Change_Valve(bool STATE, CLEANER);
  Change_Valve(bool STATE, WATER);
  Change_Valve(bool STATE, SANITIZER);
  Cleaning_Vessel_Heater(Cleaner_Temp);

    while (TRUE)
    {
      //Check if Cleaner is within 5 degrees below or above set temp
      if(Get_Cleaner_Temp >= Cleaner_Temp - 5)
      {
      //********************* RINSE CYCLE
        Change_Valve(TRUE, int $$CITY WATER VALVE); // Open City Rinse Water
        system.wait(30); 
        Change_Valve(FALSE, int $$CITY WATER VALVE); // Close City Water
        system.wait(5); // Wait For Valve To Close

      //********************* CLEAN CYCLE
        Change_Valve(TRUE, int $$CLEANER VALVE); // Open Cleaner Valve
        PUMP(TRUE); // Turn On The Pump
        system.wait(60); // Circulate the Cleaner for 60 seconds
        PUMP(TRUE); // Turn Off The Pump
        Change_Valve(FALSE, int $$CLEANER VALVE); // Close Cleaner Valve

     //********************* RINSE CLEANER
        Change_Valve(TRUE, int $$CITY WATER VALVE); // Open City Rinse Water
        system.wait(30); 
        Change_Valve(FALSE, int $$CITY WATER VALVE); // Close City Water
        system.wait(5); // Wait For Valve To Close

      //********************** SANITIZE CYCLE
        Change_Valve(TRUE, int $$SANITIZER VALVE); // Open Sanitizer Valve
        PUMP(TRUE); // Turn On The Pump
        system.wait(60); // Circulate the Sanitizer for 60 seconds
        PUMP(TRUE); // Turn Off The Pump
        Change_Valve(FALSE, int $$SANITIZER VALVE); // Close Sanitizer Valve
      }

      // Else cleaner isn't yet up to temp
      else
      {
        // Wait 10 seconds and check temp again
        wait(10);
      }
    }
}
'''



