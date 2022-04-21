# Pijuice_up_monitor
Script to monitor battery charge status of PiJuice Pi HAT against time. 


Download script onto your RasPi with the Pijuice already installed and save it in directory of choice.

Open terminal window in RasPi

In the terminal window, type the following (without quotation marks): 

  'crontab -e'
  
For more information about crontab: https://www.tutorialspoint.com/unix_commands/crontab.htm
  
Scroll to be the end of the crontab 'script' and type the following (without quotation marks), this runs the python script every minute:

  '* * * * * python3 upmonitor_3.py'
  
  
Reboot your system to start logging. In theory, the command 'sudo service cron reload' should suffice but I had mixed results with this. Rebooting was more certain to get it going.

Depending on where your directory has been set to in the python script (default is '//home/pi/uptest.txt' in line ~7), you will start populating a csv text file containing date and time, time since last boot, average loads on the CPU and Battery charge status and any battery errors. 

To stop the logging reopen crontab from the terminal window and comment out the line added at the end of it.
