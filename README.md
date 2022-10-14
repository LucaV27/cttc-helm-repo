# CTTT Helm Repo
This is a Helm Repo for CTTC (created by LucaV27).

## Install helm 
Following some guide in internet, to install helm:
```bash
sudo apt-get update && sudo apt-get upgrade -y
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh
```

## Create a Helm repo

Followed this [guide](https://medium.com/@mattiaperi/create-a-public-helm-chart-repository-with-github-pages-49b180dbb417) to create this Helm Repo in my GitHub page.

## Create a Helm chart

In the same directory of the Helm Repo, you can create a Chart by using
```bash
helm create service-adapter
```
Once done all the work to make it work
```bash
helm package service-adapter/ # to package the helm chart
helm install --dry-run service-adapter/ # to see what the chart would install
helm inspect values service-adapter/ # to have a look to the `values.yaml` file
helm repo index . # to regenerate chart index
```
Finally to push the changes to the Helm repo
```bash
git add . && gt commit -m "Commit message" && git push
```

## To use the Helm repo

```bash
helm repo add my-helm-repo https://lucav27.github.io/cttc-helm-repo/
helm install my-helm-repo/service-adapter --generate-name
```

