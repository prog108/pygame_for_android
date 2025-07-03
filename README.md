# pygame_for_android

First install buildozer on Windows: pip3 install --upgrade buildozer (or you should do that in WSL in virtual enviroment).

After downloading and installing WSL (Virtual Linux Enviroment) use next commands: 
sudo apt update
sudo apt upgrade
sudo apt install python3-pip git

Navigate to your PYGAMEfolder on Windows.
The folder where you will have your main.py or game.py, whatever.
Navigate with cd /mnt/c and so on. to the folder

pip3 install --upgrade pip
pip3 install --upgrade cython
sudo apt install -y openjdk-8-jdk unzip
sudo apt install -y python3-setuptools
sudo apt install -y libssl-dev
sudo apt install -y build-essential

ERROR: 
Receiving error after 'buildozer -v android debug': Check configuration token. It is about distutils.
In newer versions of Python (Python 3.12), distutils is not included and have to be installed like this:
pip install setuptools
pip install wheel
pip install distutils.



Ako si napravio projekt u Windowsu, to nije nemoguće koristiti, ali ćeš možda trebati dodatno podešavanje ili pokretanje alata u WSL-u ili virtualnoj mašini s Linuxom.

Za Python 3.10, distutils je često uklonjen iz standardnih paketa. Umjesto toga, preporučuje se korištenje setuptools. Međutim, ako trebate distutils za specifične potrebe, možete pokušati s instalacijom putem pip.


KIVY INSTALLATION ON UBUNTU:
1) INSTALL DEPENDENCIES: sudo apt install python3-pip python3-setuptools python3-wheel
                         sudo apt install libgl1-mesa-dev
2) INSTALL VIRTUAL ENVIROMENTS GLOBALLY IF YOU HAVEN'T ALREADY. : sudo apt install python3-venv
3) THROUGH TERMINAL NAVIGATE TO YOUR PROJECT FOLDER: python -m venv my_venv           'my_venv' is name of your choice
4) ACTIVATE THE ENVIROMENT: source moj_venv/bin/activate
5) INSTALL KIVY: pip install kivy[base]
6) YOU CAN DEACTIVATE THE ENVOROMENT FOR NOW. USE: deactivate

KIVY INSTALLTION IN VISUAL STUDIO CODE (IF YOU USE THAT EDITOR):
1) IN VSC OPEN THE PROJECT FOLDER.
2) IN TERMINAL MAKE OR ACTIVATE VIRTUAL ENVIROMENT: SAME AS STEPS 3) AND 4) IN INSTRUCTIONS JUST ABOVE: KIVY INSTALLATION FOR UBUNTU
   BE CAUTIOUS WITH THE DIRECTION OF '/'.
3) INSTALL PIP IF NEEDED: pip install --upgrade pip setuptools wheel
4) pip install kivy[base]
5) IN VSC CHANGE INTERPRETER: USE ONE WITH: my_venv/bin/python.
6) HERE YOU GO. THE MODUL KIVY IS RECOGNIZED.





Using Ubuntu:
1) sudo apt update
2) sudo apt install -y git zip unzip openjdk-17-jdk python3-pip autoconf libtool pkg-config zlib1g-dev libncurses5-dev libncursesw5-dev libtinfo5 cmake libffi-dev libssl-dev
3) HERE YOU MIGHT GET ERROR: E: Unable to locate package libtinfo5 THAT IS BECAUSE: UBUNTU VERSION: 24.04.1 LTS. DOESN'T HAVE IT PRE-INSTALLED.
  GET THE libtinfo5 with:   wget http://security.ubuntu.com/ubuntu/pool/universe/n/ncurses/libtinfo5_6.3-2ubuntu0.1_amd64.deb
  sudo apt install ./libtinfo5_6.3-2ubuntu0.1_amd64.deb
  REGARDLESS OF NOTIFICATION, TRY AGAIN STEP 2. THIS TIME IT SHOULD BE INSTALLED.
4)pip3 install --user --upgrade Cython==0.29.33 virtualenv  # the --user should be removed if you do this in a venv
5) AGAIN POSSIBLE ERROR IF THE VERSION OF UBUNTU YOU HAVE DOESN'T ALLOW THE INSTALLATIONS VIA: pip --user or pip install
6) IF ERROR ON STEP 5) OCCURS: MAKE A VIRTUAL ENVIROMENT
7) INSTALL GLOBALLY THE PROGRAM FOR VIRTUAL ENVIROMENTS: sudo apt install python3-venv
8) Navigate through terminal to your project folder and make a virtual enviroment with: python -m venv my_venv           my_venv is name of your choice
9) ACTIVATE THE ENVIROMENT: source my_venv/bin/activate
10) INSTALL CYPHON: pip3 install --user --upgrade Cython==0.29.33 virtualenv  # the --user should be removed if you do this in a venv
    INT TERMINAL TYPE INSIDE ACTIVATED VIRTUAL ENVIROMENT: pip3 install --upgrade Cython==0.29.33 virtualenv
11) deactivate 
12) # add the following line at the end of your ~/.bashrc file
    export PATH=$PATH:~/.local/bin/
13) GO TO ROOT FOLDER: cd ~
14) nano ~/.bashrc TO OPEN THE EDITOR
15) WITH THE CURSOR GO TO THE END OF FILE AND PASTE: export PATH=$PATH:~/.local/bin/
16) Ctrl + o     AND PRESS ENTER. THIS IS FOR SAVING CHANGES
17) Ctrl + x     TO EXIT THE EDITOR
18) source ~/.bashrc TO MAKE IT VALID GLOBALLY
21) IF YOU ARE ABLE YOU CAN NOW INSTALL BUILDOZER GLOBALLY. OTHERWISE USE VIRTUAL ENVIROMENT.
22) NAVIGATE AGAIN TO PROJECT FOLDER AND ACTIVATE THE ENVIROMENT
23) pip install buildozer

24) NOW YOU HAVE YOUR .APK FILE
25) EXIT THE ENVIROMENT, GO TO THE ROOT AND INSTALL ADB: sudo adb install
26) CONNECT YOUR PHONE TO THE PC WITH THE CABLE AND MAKE DEVELOPER'S MODE AVAILABLE. (INSTRUCTIONS ON OTHER PLACE IF YOU DON'T KNOW IT)
27) CHECK IF ADB FINDS YOUR PHONE: adb devices
28) YOUR PHONE WILL BE SEEN UNDER SOME UNRECOGNIZEABLE NUMBERS IN WORST CASE
29) adb install ~/PROJECT_FOLDER/bin/my_application.apk
30) AT THIS MOMENT YOUR PHONE MIGHT BLOCK THE INSTALLATION. YOU WILL BE ASKED TO ALLOW THE INSTALLATION OR STH LIKE THAT.
31) REPEAT: 29) adb install ~/PROJECT_FOLDER/bin/my_application.apk
32) THE APPLICATION SHOULD BE ON YOUR DEVICE

33) buildozer --version NOW, YOU ARE ASSURE THAT YOU HAVE BUILDOZER INSTALLED
34) buildozer init TO CREATE .spec FILE. THE NAME OF YOUR MAIN FILE SHOULD BE SAME AS HERE IN.SPEC: # (str) The name of the main Python file
                                                                                                      source.main = main.py
20) buildozer -v android debug TO CREATE .APK
