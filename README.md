You need to have vagrant set up before using commands below

To start vm run:
```shell
sudo vagrant up
```

Wait until ansible prepares vm

```shell
sudo vagrant ssh
```
Use that to run
```
working-deployment.yaml
```
and
```
not-working-deployment.yaml
```
by copying it to the vm and running
```
kubectl apply -f filename.yaml
```

To delete vm use
```shell
sudo vagrant destroy
```

To check deploy working-deployment.yaml and run
```shell
curl http://10.20.30.40/
```

Then delete working-deployment.yaml and deploy not-working-example.yaml and run
```shell
curl http://10.20.30.45/
```
Output should be the same because it is the same container, but it isn't
