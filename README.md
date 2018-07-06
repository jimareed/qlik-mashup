# qlik-mashup
Deploy a simple mashup to QSEfE.  

Prerequisites:
- install QSEfE
- install Elastic Distributor Tester (or QSEfW)

## Steps:

### 1. Distribute your App
Use Elastic Distributor Tester or QSEfW to distribute your app to QSEfE (e.g., cereal.qvf).  Open the app and note the app id in the url (e.g., https://elastic.example/sense/app/29840006-48e4-403d-a0c0-99123779b5bd)

### 2. Update the mashup .js file to point to the app id

E.g., update src/cereal/cereal.js to point to the distributed app:
```
var app = qlik.openApp('29840006-48e4-403d-a0c0-99123779b5bd', config);
```

### 3. Install the chart:
```
$ helm install --name qlik-mashup ./chart/qlik-mashup
```

> browse to https://elastic.example/extensions/cereal/cereal.html
