## Cannon GameBot

This repository contains code for an AI bot designed to play Cannon, an abstract strategy board game, designed by [@adityanathan](https://github.com/adityanathan) and [@dwijesh522](https://github.com/dwijesh522). It also contains code for a simulator supporting a user interface for Cannon as described [here](cannon_client_instructions.md).

[Demo](https://youtu.be/gslh80uPSDY) - Sample game where the designed bot plays against itself

# Execution

To execute a sample game where the designed AI bot plays against itself, see the following instructions:

- Install python dependencies from the [requirements.txt](requirements.txt) file (Note: You need Python 2.7 to run the simulator)

        python2 -m pip install -r requirements.txt

- Download the chrome driver executable according to your chrome version from [here](https://chromedriver.chromium.org/downloads). To check your chrome version in order to download the appropriate chrome driver, follow the steps below:
    + Launch Google Chrome.
    + Click on the icon in the upper right corner that looks like 3 short bars.
    + Select About Google Chrome to display the version number.
    + Download the appropriate chrome driver executable

- Compile the GameBot using the [compile script](GameBot/compile.sh) provided

        cd GameBot
        sh compile.sh

- Run the simulator [server](server.py)

        python2 server.py 10000 -n 8 -m 8 -NC 2 -TL 150 -LOG server.log

- Instantiate a simulator [client](client.py) for a player

        export PATH=$PATH:</home/chrome_driver_directory_path>
        python2 client.py 0.0.0.0 10000 run.sh

- Instantiate another simulator client for the opponent player

        python2 client.py 0.0.0.0 10000 run.sh