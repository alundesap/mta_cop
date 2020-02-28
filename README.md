cop Application

Build Command:

```
cd mta_cop ; mkdir -p target ; mbt build -p=xsa -t=target --mtar=mta_cop.mtar
```

Build Command:

```
cd mta_cop ; mkdir -p target ; mbt build -p=cf -t=target --mtar=mta_cop.mtar
```

Deploy Command:
```
xs deploy target/mta_cop.mtar -f -e deploy2xsa.mtaext
```

Deploy Command:

```
cf deploy target/mta_cop.mtar -f
```

Undeploy Command:
```
xs undeploy cop -f --delete-services
```

Undeploy Command:

```
cf undeploy cop -f --delete-services
```
cf ssh-code ; ssh -nNT -p 2222 cf:1b263104-48c8-4a27-abf9-561e3842d369/0@ssh.cf.us10.hana.ondemand.com -L 5678:localhost:5678

export GUID=$(cf app cop-pyt --guid) ; echo $GUID

!!!
export GUID=$(cf app cop-pyt --guid) ; echo $GUID ; cf ssh-code ; ssh -nNT -p 2222 cf:$GUID/0@ssh.cf.us10.hana.ondand.com -L 5678:localhost:5678
!!!

cf push cop-pyt -p python -m 256M -k 512M -u none
cf enable-ssh cop-pyt
