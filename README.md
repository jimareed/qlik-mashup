# qlik-mashup
Deploy a simple mashup to QSEfE.  

## Prerequisites:
- install QSEfE
- install Elastic Distributor Tester (or QSEfW)
- clone this repo

## Steps:

#### 1. Distribute your App
Use Elastic Distributor Tester or QSEfW to distribute your app to QSEfE (e.g., cereal.qvf).

#### 2. Install the chart:
```
$ helm install --name qlik-mashup ./chart/qlik-mashup
```

> browse to https://elastic.example/extensions/cereal/cereal.html


## Update the mashup
Here are the steps required to update the mashup.

#### 1. Update the mashup in the src folder

#### 2. Build the docker image locally
```
docker build --tag qlik-mashup .
```

#### 3. Change the helm chart values file to point to your local docker image
change ./chart/qlik-mashup/values.yaml to point to the image you just built
```
repository: qlik-mashup
```

#### 4. Upgrade the chart
```
helm upgrade qlik-mashup ./chart/qlik-mashup
```
