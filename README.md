# reeve
Shell script to install a [reeve Masternode](http://reevecoin.com/) on a Linux server running Ubuntu 16.04. Use it on your own risk.

***
## Installation:
```
wget -q https://raw.githubusercontent.com/reevecoin/reevemn/master/reeve_install.sh
bash reeve_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open **Reeve Wallet**.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **10000** **Reeve** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is un
12. Select your MN and click **Start Alias** to start it.
***

## Usage:
```
reeve-cli mnsync status
reeve-cli getinfo
reeve-cli masternode status #This command will show your masternode status
```

Also, if you want to check/start/stop **reeve** , run one of the following commands as **root**:

```
systemctl status reeve #To check the service is running.
systemctl start reeve #To start reeve service.
systemctl stop reeve #To stop reeve service.
systemctl is-enabled reeve #To check whetether reeve service is enabled on boot or not.
```
***

## Issues:
If your reeve Core Wallet doesn't sync, go to **Tools -> Open Wallet Configuration File** and add the following entries:
```
addnode=188.225.77.200
addnode=188.225.77.197
addnode=188.225.77.196
addnode=188.225.33.132
addnode=188.225.75.144
addnode=188.225.75.17
addnode=188.225.77.191
addnode=188.225.10.82
```

