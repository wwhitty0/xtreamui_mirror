# README #
# xtreamui_mirror for ubuntu 20

updated php binaries to make it work with ubuntu 20 and curl4.  
i have compiled php 7.2 on ubuntu 18, installed panel, then runned make install command, it installed compiled binaries to panel's php folder.  
then i zipped this php folder, deleted 3 conf that related for main server file from php/etc folder.  
now if you want to update only php files (even on ubuntu 18), just unzip php_7.2.33_for_xc.zip and you will be ready to go.  

added mysql server 8 (for ubuntu 20) and a working my.cnf with this install.py  
added some sed commands to replace python commands with python2, yes python2 on ubuntu 20.  

tested few basic things like live streams, user adding, watch stream on user side.  

rest of files are same, main_xtreamcodes_reborn.tar and sub_xtreamcodes_reborn.tar are still same files from original install.py. i didn't want to add/change anything else, you must change other things if you wish.  


### How do I install? ###

update your ubuntu first, then install panel  
  
* sudo apt-get update && sudo apt-get upgrade -y && sudo apt-get install python2 -y;  
* wget https://github.com/emre1393/xtreamui_mirror/raw/master/ubuntu20/install.py; 
* sudo python2 install.py  
  
If you want a whole NEW installation, choose MAIN and then UPDATE.  
If you want to install load balance on additional servers, add a server to panel in manage servers page, then run script and proceed with LB option.  
If you want to update admin panel, select UPDATE, then paste download link of release_xyz.zip file.  

### tutorials are here; ###

[Xtream-UI Tutorials](https://www.youtube.com/playlist?list=PLJB51brdC_w7dTDxi1MPqiuk3JH5U2ekn "Xtream-UI Tutorials")


### Files Hashes ###
* main_xtreamcodes_reborn.tar
* sha1: "532B63EA0FEA4E6433FC47C3B8E65D8A90D5A4E9"

* sub_xtreamcodes_reborn.tar
* sha1: "5F8A7643A9E7692108E8B40D0297A7A5E4423870"

### note,
i forked this install.py is from https://xtream-ui.com/install/install.py  
btw, developer removed admin part from original install.py at begining of this year.  
you can compare my install.py with original one.

### note2,
edit pytools/balancer.py to use "auto lb installer" from this mirror. auto lb installer added to panel with update    
`sed -i 's|"https://xtream-ui.com/install/balancer.py"|"https://github.com/emre1393/xtreamui_mirror/raw/master/ubuntu20/balancer.py"|g' /home/xtreamcodes/iptv_xtream_codes/pytools/balancer.py`  

### note3,  
developer made update releases open to public after r22c release, you can download them from https://xtream-ui.com.  
i added an "UPDATE" part to install.py, it will ask link of update zip file.  

### note4,  
updated php binaries with php 7.2.33 version, compiled according to the how-to txt
my.cnf config for mysql server 8