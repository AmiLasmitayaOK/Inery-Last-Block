# How to
```
sudo apt update && sudo apt upgrade -y && sudo apt install zip unzip
```
```
wget --load-cookies /tmp/cookies.txt "https://drive.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://drive.google.com/uc?export=download&id=1w0DvS7InQCZkpPnoMUWeYczo2TeTevj8' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=1w0DvS7InQCZkpPnoMUWeYczo2TeTevj8" -O blockchain.zip && rm -rf /tmp/cookies.txt
```
```
unzip blockchain.zip
```
```
cd $HOME/inery-node/inery.setup/master.node/
./stop.sh
./clean.sh
```
```
cp -r $HOME/blockchain $HOME/inery-node/inery.setup/master.node/blockchain
```
```
cd $HOME/inery-node/inery.setup/master.node/
./start.sh
```
```
cd
rm -rf blockchain
rm -rf blockchain.zip
```
Check hasilnya setelah 10-30 an menit :
```
cd 
curl -sSL -X POST 'http://localhost:8888/v1/chain/get_info' -H 'Accept: application/json' | jq
```

#### Check Log
```
cd $HOME/inery-node/inery.setup/master.node/
tail -f blockchain/nodine.log
```
