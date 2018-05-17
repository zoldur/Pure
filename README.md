# Pure
Shell script to install a [Pure Masternode](https://purealt.org) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
wget -q https://raw.githubusercontent.com/zoldur/Pure/master/pure_install.sh
bash pure_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Pure Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **5000** PURE to **MN1**. You need to send all 5000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs**  
7. Go to **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
9. Save and close the file.
10. Open **Debug Console** and type:
```
masternode start-alias MN1
```
11. Login to your VPS and check your masternode status by running the following command.
```
pure-cli masternode status
```
***

## Usage:
```
pure-cli mnsync status
pure-cli masternode status  
pure-cli getinfo
```
Also, if you want to check/start/stop **Pure**, run one of the following commands as **root**:

```
systemctl status Pure #To check if Pure2 service is running
systemctl start Pure #To start Pure2 service
systemctl stop Pure #To stop Pure2 service
systemctl is-enabled Pure #To check if Pure2 service is enabled on boot
```  
***

## Donations

Any donation is highly appreciated

**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x26B9dDa0616FE0759273D651e77Fe7dd7751E01E  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB  
