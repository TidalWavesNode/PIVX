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
1. Open the PIVX Core Wallet.
2. Go to RECEIVE and create a New Address: **MN01**
3. Send **10,000** **PIVX** to **MN01**.
4. Wait for 15 confirmations before starting the node.
5. Go to **Help -> "Debug window - Console"**
6. Type the following command: **masternode outputs**
7. Open masternode.conf from the following folder %appdata%\obsr (windows) or ~/Library/Application Support/ (hidden folder for Mac users)
8. Add the following entry:
```
Alias Address Genkey TxHash Output_index
```
* Alias: **MN01**
* Address: **VPS_IP:51472**
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

pivx-cli getinfo

pivx-cli masternode status

Also, if you want to check/start/stop **PIVX** , run one of the following commands as **root**:

systemctl status PIVX #To check the service is running.

systemctl start PIVX #To start Observer service.

systemctl stop PIVX #To stop Observer service.

systemctl is-enabled Observer #To check whether PIVX service is enabled on boot or not.

***
# Donations
$PIVX: D6m95LwH3HTBBLg5tN1nnBtpvjETq9mk5e
