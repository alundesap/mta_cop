cop Application

Build Command:
```
cd mta_cop ; mkdir -p target ; mbt build -p=cf -t=target --mtar=mta_cop.mtar
```

Deploy Command:
```
cf deploy target/mta_cop.mtar -f
```

Undeploy Command:
```
cf undeploy cop -f --delete-services
```
