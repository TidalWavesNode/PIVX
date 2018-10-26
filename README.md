# PIVX
Shell script to install an [PIVX Masternode](https://pivx.org/) on a Linux server running Ubuntu 16.04 and above.  
This will require a VPS running Ubuntu 16.04 or higher and installs **PIVX Core 3.1.1**.
***

## Installation:
Log into the server using ssh (Putty for windows or terminal for Mac users) and run the following commands:

wget -q https://raw.githubusercontent.com/TidalWavesNode/PIVX/master/setup.sh

bash setup.sh

***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows/Mac Wallet:
1. Open the Observer Core Wallet.
2. Go to RECEIVE and create a New Address: **MN01**
3. Send **1,000,000** **OBSR** to **MN01**.
4. Wait for 15 confirmations before starting the node.
5. Go to **Help -> "Debug window - Console"**
6. Type the following command: **masternode outputs**
7. Open masternode.conf from the following folder %appdata%\obsr (windows) or ~/Library/Application Support/ (hidden folder for Mac users)
8. Add the following entry:
```
Alias Address Genkey TxHash Output_index
```
* Alias: **MN01**
* Address: **VPS_IP:9567**
* Genkey: **Masternode GenKey**
* TxHash: **First value from Step 6** 
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. Click OK and exit the Wallet.
10. Open Observer Core Wallet, go to **Masternode Tab**.
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
10. Click **Start All** or **Start Alias**
11. If you are not able to see your **Masternode**, try to close and open your desktop wallet.
***

## Usage:

obsr-cli getinfo

obsr-cli masternode status

Also, if you want to check/start/stop **Observer** , run one of the following commands as **root**:

systemctl status Observer #To check the service is running.

systemctl start Observer #To start Observer service.

systemctl stop Observer #To stop Observer service.

systemctl is-enabled Observer #To check whether Observer service is enabled on boot or not.

***
# Donations
$OBSR: odaumHKFxC8WXhrpX4MhviqU7WTX23DS3r
