# UltraAndVolumio
This workaround allows you to use VOLUMIO on a Raspberry PI with an ULTRA+ sound card

###### (the  WS driver cannot be installed for the moment...)

## How to install it ?
1. Install Volumio on a SD
2. Initialize Volumio as usual and choose "raspiaudio" in the "i2s" section
3. On the RasberryPI directly or via "ssh" do these operations:
     * A. Load this repositery :
     
        ###### => git clone https://github.com/RASPIAUDIO/UltraAndVolumio.git
     * B. Validate "ultra":
     
         #### directly:
         
         ###### => cd UltraAndVolumio
         
         ###### => chmod 777 ultra  
      
          #### OR create it from the source file ultra.c:
          
          ###### => gcc -o ultra ultra.c
          
         ("gcc" may not be available on the standard Volumio distrib!...) 
            
     * C. Prepare the execution of "ultra" every time Volumio starts:
     
          you have to add this line: "/home/volumio/UltraAndVolumio/ultra&"
             
          in the file "/etc/rc.local" just before the line "exit 0"
              
          for this you can use "nano":
              
          ###### => sudo nano /etc/rc.local
 4. restart:
 
      ##### => reboot
     



