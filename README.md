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
cd
mv $HOME/blockchain $HOME/inery-node/inery.setup/master.node/blockchain
rm -rf $HOME/blockchain.zip
source ~/.bashrc && which nodine || source ~/.bash_profile
```
```
cd $HOME/inery-node/inery.setup/master.node/
./hard_replay.sh
./start.sh
```

#### Check Log

```
cd $HOME/inery-node/inery.setup/master.node/
tail -f blockchain/nodine.log
```

______________


Check berhasil kagaknya setelah 3-5 jam :

```
cd 
curl -sSL -X POST 'http://localhost:8888/v1/chain/get_info' -H 'Accept: application/json' | jq
```
