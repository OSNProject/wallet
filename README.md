# wallet
OSN Project

This is the official  sourcecode repository based on KomodoPlatform/komodo.

Development Resources:
- OSN Website: https://osnproject.online
- Komodo Platform: https://komodoplatform.com
- OSN Blockexplorer: https: http://91.231.187.20:3003
- OSN Discord: https: https://discord.gg/PCcwaQ
- BTT ANN: https:
- Mail: 
- Support: discord
- Dev Documentation: https://docs.komodoplatform.com
- Whitepaper: 

Komodo Platform Technologies Integrated In OSN Project:
- zk-SNARKs - Komodo Platform's privacy technology for shielded transactions

Tech Specification:
- Max Supply: 200 million OSN
- Block Time: 60s
- Block Reward: 120 OSN
- Mining Algorithm: Equihash 200,9


Getting started:
Dependencies

#The following packages are needed:
sudo apt-get install build-essential pkg-config libc6-dev m4 g++-multilib autoconf libtool ncurses-dev unzip git python python-zmq zlib1g-dev wget libcurl4-gnutls-dev bsdmainutils automake curl libsodium-dev


Build Komodo:
This software is based on zcash and considered experimental and is continously undergoing heavy development.
At no point of time do the Komodo Platform developers take any responsbility for any damage out of the usage of this software. Komodo builds for all operating systems out of the same codebase. Follow the OS specific instructions from below.

Linux

git clone https://github.com/komodoplatform/komodo --branch master --single-branch
cd komodo
./zcutil/fetch-params.sh
./zcutil/build.sh -j$(expr $(nproc) - 1)
#This can take some time.
#Command to run PSP blockchain and connect with the network:
./komodod -ac_name=OSN -ac_supply=20000000 -ac_reward=12000000000 -ac_halving=525600 -ac_decay=65000000 -addnode=91.231.187.21 &


OSX
Ensure you have brew and the command line tools installed:

# Install brew
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
# Install Xcode, opens a pop-up window to install CLT without installing the entire Xcode package
xcode-select --install 
# Update brew and install dependencies
brew update
brew upgrade
brew tap discoteq/discoteq; brew install flock
brew install autoconf autogen automake
brew update && brew install gcc@8
brew install binutils
brew install protobuf
brew install coreutils
brew install wget
# Clone the Komodo repo
git clone https://github.com/komodoplatform/komodo --branch master --single-branch
# Change master branch to other branch you wish to compile
cd komodo
./zcutil/fetch-params.sh
./zcutil/build-mac.sh -j$(expr $(sysctl -n hw.ncpu) - 1)
# This can take some time.
#Command to run PSP blockchain and connect with the network:
./komodod -ac_name=OSN -ac_supply=20000000 -ac_reward=12000000000 -ac_halving=525600 -ac_decay=65000000 -addnode=91.231.187.21 &

Windows
Use a debian cross-compilation setup with mingw for windows and run:

sudo apt-get install build-essential pkg-config libc6-dev m4 g++-multilib autoconf libtool ncurses-dev unzip git python python-zmq zlib1g-dev wget libcurl4-gnutls-dev bsdmainutils automake curl cmake mingw-w64 libsodium-dev libevent-dev
curl https://sh.rustup.rs -sSf | sh
source $HOME/.cargo/env
rustup target add x86_64-pc-windows-gnu
git clone https://github.com/jl777/komodo --branch master --single-branch
cd komodo
./zcutil/fetch-params.sh
./zcutil/build-win.sh -j$(expr $(nproc) - 1)
#This can take some time.
#Command to run PSP blockchain and connect with the network:
./komodo-qt-win.exe -ac_name=OSN -ac_supply=20000000 -ac_reward=12000000000 -ac_halving=525600 -ac_decay=65000000 -addnode=91.231.187.21 &




OSN Project is experimental and a work-in-progress. Use at your own risk.

To reset the PirateChain blockchain change into the 

~/.komodo/OSN 

data directory and delete the corresponding files by running rm -rf blocks chainstate debug.log komodostate db.log and restart daemon

OSN Project is based on Komodo which is unfinished and highly experimental. Use at your own risk.


DOCUMENTATION
Getting Started

Agama now supports OSN! Download the latest Agama here.
To get started with OSN, you only need Komodo Platform daemon installed on your machine. You can either download the wallet from Komodo Platform website and use the bundled "komodod" and "komodo-cli" in it, or you can also compile it on your machine. Installation instructions are available on Komodo Platform documentation website here: https://docs.komodoplatform.com/komodo/install-Komodo-manually.html

Connect to OSN blockchain
Command to run OSN blockchain and connect with the network:

./komodod -ac_name=OSN -ac_supply=20000000 -ac_reward=12000000000 -ac_halving=525600 -ac_decay=65000000 -addnode=91.231.187.21 &

Wallet commands:
# Get (transparent) wallet and blockchain info
./komodo-cli -ac_name=OSN getinfo


# Get (transparent) wallet information
./komodo-cli -ac_name=OSN getwalletinfo
# Get mining information
./komodo-cli -ac_name=OSN getmininginfo
# Generate a new address
./komodo-cli -ac_name=OSN getnewaddress

# Example:
komodo-cli -ac_name=OSN sendfrom "" address  


License
For license information see the file COPYING.
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
