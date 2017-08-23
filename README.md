# monkeylines
Tossing some monkeywrenches into some pipelines and watching what happens

## clustermonkey
### Preparations:
Create pipeline (and start jenkins)
```
oc process -f templates/monkeyline.json -p GIT_CONTEXT_DIR=pipelines/clustermonkey | oc apply -f -
```
```
oc adm policy add-cluster-role-to-user cluster-admin system:serviceaccount:myproject:jenkins
```
This will grant the jenkins serviceaccount in myproject cluster-admin role (possibly overkill, and bad)