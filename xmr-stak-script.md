# sudo apt-get update
# sudo apt install libmicrohttpd-dev libssl-dev cmake build-essential libhwloc-dev
# sudo apt install cmake
# sudo apt-get install libssl-dev
# sudo apt-get install libhwloc-dev
# sudo apt-get install -y hwloc
# sudo sysctl -w vm.nr_hugepages=128
# sudo apt install vim

git clone https://github.com/fireice-uk/xmr-stak.git
mkdir xmr-stak/build
cd xmr-stak/build
cmake .. -DCUDA_ENABLE=OFF  -DOpenCL_ENABLE=OFF
make install

cd Documentos
nano simple_script.sh

#/!usr/bin/env bash
cd /xmr-stak/build/bin
./xmr-stak/build/bin/xmr-stak --currency monero -o xmrpool.eu:3333 -u 47BuFWQ1jF6bshb1n2DcxaVPLwNFQVqKi7kV6uWFxWpSe9B3R93arEKQdr8DsBcanZ9zyqFywaYitc5PRBUxaXRoMjAWjrr

sudo cp /home/ufabc/Documentos/simple_script.sh /etc/init.d/
sudo chmod a+x /etc/init.d/simple_script.sh
sudo chmod 777 /etc/init.d/simple_script.sh

sudo crontab -e
@ reboot /home/ufabc/Documentos/simple_script.sh


// para rodar o xmr-stak:
sudo sysctl -w vm.nr_hugepages=128
./xmr-stak/build/bin/xmr-stak --currency monero -o xmrpool.eu:3333 -u 47BuFWQ1jF6bshb1n2DcxaVPLwNFQVqKi7kV6uWFxWpSe9B3R93arEKQdr8DsBcanZ9zyqFywaYitc5PRBUxaXRoMjAWjrr

sudo sysctl -w vm.nr_hugepages=128; ./xmr-stak/build/bin/xmr-stak --currency monero -o xmrpool.eu:3333 -u 47BuFWQ1jF6bshb1n2DcxaVPLwNFQVqKi7kV6uWFxWpSe9B3R93arEKQdr8DsBcanZ9zyqFywaYitc5PRBUxaXRoMjAWjrr; echo -ne '\n'; echo -ne '\n'

ExecStart=/home/aniket/xmr-stak.sh -c YOURCONFIGFILELOCATION

https://www.cryptocurrencyfreak.com/2017/08/22/monero-mining-xmr-stak-cpu-ubuntu-16-04/
