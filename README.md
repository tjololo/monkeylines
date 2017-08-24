# monkeylines
Tossing some monkeywrenches into some pipelines and watching what happens

## clustermonkey
### Preparations:
Create pipeline (and start jenkins)
```
oc process -f templates/monkeyline.json -p GIT_CONTEXT_DIR=pipelines/clustermonkey | oc apply -f -
```
Grant the jenkins serviceaccount in myproject cluster-admin role (possibly overkill, and bad)
```
oc adm policy add-cluster-role-to-user cluster-admin system:serviceaccount:myproject:jenkins
```
Unfortunately you have to manually update the Pipeline Utility Steps plugin to get the readJSON functionality this pipeline uses
