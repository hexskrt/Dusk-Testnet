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

That's all for now, wait for the next step
