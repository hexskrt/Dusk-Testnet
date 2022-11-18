# Tutorial Incentivized Dusk Testnet

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202432156-50a53f84-3d5d-40da-950c-0d9e62c2e4b4.jpg">
</p>

## Referensi

[Official Documentation](https://dusk.network/pages/incentivized-testnet#Wallet)

[Ask Faucet](https://docs.google.com/forms/d/e/1FAIpQLScxABRnszbBEaTZAIg2TwfJVIq0kRggy8QK2MRBTO7vuyP_Ug/viewform)

[Discord Server](https://discord.gg/dusknetwork)

## Requirements

### Hardware Requirement

| Componen | Minimum Requirement |
|----------|---------------------|
|CPU|Intel Core 2|
|RAM|1 GB DDR4 RAM|
|Storage|20 GB HDD|

### Software Requirement

| Componen | Minimum Requirement |
|----------|---------------------|
|OS|Ubuntu 20.04|

| Componen | Recomended Requirement |
|----------|---------------------|
|OS|Ubuntu 20.04 atau Higher|

## 1. Install CLI

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202432162-68e7828e-e917-4636-83a4-5c7969356313.png">
</p>

```
sudo apt-get update
```
```
wget -q https://github.com/dusk-network/wallet-cli/releases/download/v0.12.0/ruskwallet0.12.0-linux-x64.tar.gz
```
```
tar -xf ruskwallet0.12.0-linux-x64.tar.gz
```
```
rm -rf ruskwallet0.12.0-linux-x64.tar.gz
```
```
cd rusk-wallet0.12.0-linux-x64
```
```
./rusk-wallet
```

## 2. Create Wallet

- Choose 'Create New Wallet' , Press Enter
- Enter Your Password
- Enter Password Again
- Copy and Save Your Pharse
- Select 'y' and 'Enter'
- it Will Show Your Address Copy And Save It

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202432143-2ca75493-230f-441a-9389-7165b80019f0.jpg">
</p>

- Use Your Keyboard Arrow
- Navigate to 'Export Provisioner Key-Pair' and 'Enter'
- Then Fill In With The Command Below, Depending On Your Own Directory Placement

Example:
```
/root/.dusk/rusk-wallet/
```
- Then Press 'Enter' You Will See The Image Below, Don't forget to save the ones I've bookmarked 

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202432152-3e5578a6-9b21-4cd2-adab-8b132fd111d4.PNG">
</p>

**Noted :** There should be two files now, a .key file and a .cpk file. Keep .key files private, don't share them with anyone. You will need this file later for next step. That is like consensus key, which you use to sign transactions.

.cpk is public key. You will need this one to give you for access testnet


- Back to VPS Press Your Keyboard and Choose 'Back' and 'Enter'
- Down Again Select 'Exit' and 'Enter'

## 3. Ask Faucet

- Fill This Form For Faucet : https://docs.google.com/forms/d/e/1FAIpQLScxABRnszbBEaTZAIg2TwfJVIq0kRggy8QK2MRBTO7vuyP_Ug/viewform
- Paste your Dusk Address
- Upload your File.cpk 
- Fill Reward address with your ETH Metamask Address (This is To Receive The Testnet Reward Later)
- Submit Form

Noted: File.cpk is located in `.dusk`

## 4. Making Sure the Faucet Is Landing

- Open your Vps
- To Confirm Whether the Faucet Balance Has Landed, Run the Command Below :

```
cd rusk-wallet0.12.0-linux-x64
./rusk-wallet
```

- Down Direction Select 'Replace your wallet with a lost one using the recovery phrase' and 'enter'
- Put your Pharse Wallet 'Enter'
- Enter your Password 2x and 'Enter'
- Back to VPS Downward Select 'Back' and 'Enter'
- Down Again Select 'Exit' and 'Enter'

## 5. Instal Rusk-Node

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202716202-a9687681-6daa-4a5f-b1d7-299f0d72e2f7.JPG">
</p>

```
cd
curl --proto '=https' --tlsv1.2 -sSf https://dusk-infra.ams3.digitaloceanspaces.com/rusk/itn-installer.sh | sh
```

## 6. Open Port (For Azure Users the same DO usually Open Port on Your VPS Dashboard Website) if Contabo Just Paste it directly on your VPS

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202716199-ff3752f6-76a4-4cab-965b-3a13b7f12623.jpg">
</p>

```
sudo ufw allow 22
sudo ufw allow 9000:9005/udp
sudo ufw enable
```

## 7. Set password 'consensus.keys' Run

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202716195-647652a1-e758-477a-850e-7c002a0102f9.jpg">
</p>

```
cd /root/.dusk/rusk-wallet
mv *.key /opt/dusk/conf/consensus.keys
```
```
echo 'DUSK_CONSENSUS_KEYS_PASS=<insert_your_password>' > /opt/dusk/services/dusk.conf
```

'<insert_your_password>' = fill in with your password, just like the same that just started to create a wallet

## 8. Start Node

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202716190-b364ac77-2424-4693-b7af-37157cc9a2e9.jpg">
</p>

```
service rusk start
service dusk start
```

If It Doesn't Happen Anything That's Means Right

## 9. Check Rusk and Dusk Logs (To Ensure It's Working)

### Check rusk logs

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202716183-094af1f4-eab6-4f95-a021-45ed26c4406d.jpg">
</p>

```
tail -f /var/log/rusk.log
```

### Check dusk logs

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202716177-8a814b33-8205-40ef-a4be-0fe6ee9d997c.jpg">
</p>

```
tail -f /var/log/dusk.log
```


## 10. Stake Token

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202719383-9e0c6c50-157a-4cdb-a2ee-6b55cc9c26f5.JPG">
</p>

```
cd
cd rusk-wallet0.12.0-linux-x64
./rusk-wallet
```

- Select 'Access Wallet' and 'Enter'
- Enter Your Password and 'Enter'
- Then 'Enter' again
- Direction Down Select 'Stake Dusk' 
- Insert the amount of DUSK to stake: contents '25000' and 'Enter'
- Insert the gas limit for this transaction: contents '2000000000 and 'Enter'
- Insert the gas price for this transaction: Let It Go 'Enter' Directly
- Type 'y' and 'Enter'
- Done

## Checking Staking If Already Works

<p align="center">
  <img height="auto" width="auto" src="https://user-images.githubusercontent.com/38981255/202719371-a190234a-6fa5-4174-b8c9-1918c0ebbd3a.JPG">
</p>

```
./rusk-wallet
```

- Select 'Access Wallet' and 'Enter'
- Enter Your Password and 'Enter'
- Then 'Enter' again
- Down Direction Select 'Check existing stake' and 'Enter'
- Done

## 12. Other Useful Commands

## Running the service

### Running service rusk

```
service rusk start
```

### Running dusk service

```
service dusk start
```

## Stop the service

### Stop rusk service

```
service rusk stop
```

### Stop dusk service

```
service dusk stop
```
