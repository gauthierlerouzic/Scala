## How to mine Scala with a Raspberry PI

I tried this with a Raspberry Pi 3B+ with the SO Raspbian. If you try with other RPI model or other SO, send me a message and I can update the table.


| MODEL | SO | Hashrate(H/s) | Comments |
| ----- | ---- | ---- | ---- |
| 3B | Raspbian OS 64 bits | 50/90 | with that SO you can skip steps 3 and 4|
| 3B+ | Raspbian | 100 | |
| 3B+ | Raspbian OS 64 bits | 100 | with that SO you can skip steps 3 and 4|
| 4 | Raspbian Lite | 200 | |


1. Firts of all, update your RPI.

`sudo apt update`

`sudo apt full-upgrade`


2. Reboot if necessary.

`sudo shutdown -r now`


3. Now, install the ds64-shell. You can run 64 bit programs with it.

`sudo apt-get install -y raspbian-nspawn-64`


4. Start it with:

`ds64-shell`


5. Install the needed dependencies.

`sudo apt-get install git build-essential cmake libuv1-dev libssl-dev libhwloc-dev`


6. Download the latest XLArig and compile it.

`git clone https://github.com/scala-network/XLArig.git`

`cd XLArig`

`mkdir build`

`cd build`

`cmake ..`

`make`


7. Give the miner execution rights.

`chmod u+x xlarig`


8. Start minning with...

`./xlarig --donate-level 0 -o scala.pooldemineria.com:3333 -u YOUR_SCALA_WALLET_ADDRESS -p YOUR_WORKER_NAME -a panthera -k`

or after reboot :

`./XLArig/build/xlarig --donate-level 0 -o scala.pooldemineria.com:3333 -u YOUR_SCALA_WALLET_ADDRESS -p YOUR_WORKER_NAME -a panthera -k`

Don't forget to update the minerpool.url by yours, YOUR_SCALA_WALLET_ADDRESS and YOUR_WORKER_NAME too
