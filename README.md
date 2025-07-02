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
