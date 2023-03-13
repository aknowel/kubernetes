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

To check deploy working-example.yaml and open browser with
http://192.168.121.40/


Then deploy not-working-example.yaml open browser with
http://192.168.121.45/

Output should be the same because it is the same container, but it isn't
