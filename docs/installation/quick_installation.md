## Copy and paste
**for local, docker usage**  

* "None informaticians / newcomer to bioinformatics" approach using ubuntu [admin rights required]


och irgendwo adden das wir das nicht recommenden da eine ältere version von docker installiert wird und auch adden das dies für "single computer anwendung ist

```bash
sudo apt-get update
sudo apt install -y default-jre
curl -s https://get.nextflow.io | bash 
sudo mv nextflow /usr/bin/
sudo apt-get install -y docker-ce docker-ce-cli containerd.io
sudo usermod -a -G docker $USER
```

* Restart your computer