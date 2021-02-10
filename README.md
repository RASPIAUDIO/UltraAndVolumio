# UltraAndVolumio
This workaround allows you to use VOLUMIO on a Raspberry PI with an ULTRA+ sound card, the I2C init sequence will be sent to the codec at each boot.

###### (the  WS driver cannot be installed for the moment...)

## How to install it ?
1. Install Volumio on a SD card
2. Initialize Volumio as usual and in the user interface choose "raspiaudio" in the "i2s" section, also for "Volume Option" choose "Mixer Type" "Software"
3. On the RasberryPI directly or via "ssh" do these operations:
     * A. Load this repositery :
     
        ###### => git clone https://github.com/RASPIAUDIO/UltraAndVolumio.git
     * B. Validate "ultra":
     
         #### directly:
         
         ###### => cd UltraAndVolumio
         
         ###### => chmod 777 ultra  
         
      
          #### Optional : you can also create you own executable from the source file ultra.c (skip this step if you completed the previous step):
          
          ###### => gcc -o ultra ultra.c
          
         ("gcc" may not be available on the standard Volumio distrib so you might have to install it!...) 
            
     * C. Prepare the execution of "ultra" every time Volumio starts:
     
          in the file "/etc/rc.local" before the line "exit 0"
          you have to add this line: "/home/volumio/UltraAndVolumio/ultra&"    
          for this you can use "nano":
              
          ###### => sudo nano /etc/rc.local
 4. restart:
 
      ##### => reboot
     
     Enjoy!



