## Copy and paste
**for local, docker usage**  

* "None informaticians / newcomer to bioinformatics" approach using ubuntu [admin rights required]
* open your terminal by pressing `STRG` + `ALT` + `T`

```bash
sudo apt-get update
sudo apt install -y default-jre
curl -s https://get.nextflow.io | bash 
sudo mv nextflow /usr/bin/
sudo apt-get install -y docker-ce docker-ce-cli containerd.io
sudo usermod -a -G docker $USER
```

* Restart your computer