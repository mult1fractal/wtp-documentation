## Install Java runtime and Nextflow

Nextflow is quite easy to install:

* install a java run time for Nextflow if not available

```bash
sudo apt-get update
sudo apt install -y default-jre
```
* install [nextflow](https://www.nextflow.io/):

```bash
# download
curl -s https://get.nextflow.io | bash 
# move to any $PATH location or add it to $PATH
# e.g.
sudo mv nextflow /usr/bin/
```

## Update Nextflow to a newer version

* just excecute this:
* alternatively use the "build in" `nextflow upgrade`

```bash
# downloads the newer version
curl -s https://get.nextflow.io | bash
# replace the old version with the newer version
sudo mv nextflow /usr/bin/
```

## Specific Nextflow versions

* if you need a specific older nextflow version for some reason, go to the [release page](https://github.com/nextflow-io/nextflow/releases)
   * under assets you find a file called "nextflow-RELEASENUMBER-all" (replace RELEASENUMBER with the actual number they provide on the release page)
   * download this file and move it to e.g. `/usr/bin/` or call it directly `./nextflow-RELEASENUMBER-all run ...`
   * instead of `nextflow run ...` you do `nextflow-RELEASENUMBER-all run ...`
