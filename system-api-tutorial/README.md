## syscalls

```
toolbox
ps aux | grep ssh
strace -p 
```

Inside toolbox:
```
md5sum /usr/lib64/libm.so.6
```

Outside toolbox: 
```
md5sum /usr/lib64/libm.so.6
```

## omaha

```
journalctl -u update-engine
```

## namespaces

```
ps aux | grep nginx
nsenter -n -t 847
```

## cgroups

```
cd /sys/fs/cgroups/
cat /sys/fs/cgroup/memory/system.slice/etcd2.service/memory.limit_in_bytes
```

## docker 

```
systemd-run ncat -vlk 1111 -c 'ncat -U /var/run/fleet.sock'
curl localhost:1111/containers/json
```

## fleet

```
systemd-run ncat -vlk 1337 -c 'ncat -U /var/run/fleet.sock'
curl http://localhost:1337/fleet/v1/state?alt=json
```

## dbus + systemd

```
dbus-monitor --system
sudo systemd-run sleep 60
```

## etcd

```
etcdctl --debug -o json set foobar baz
etcdctl --debug -o json set --swap-with-index 11282 foobar baz2
```

## k8s

```
kubectl run-container my-nginx --image=nginx --replicas=1 --port=80
```

```
curl http://192.168.168.154:59101/api/v1beta3/pods
curl http://192.168.168.154:59101/api/v1beta3/nodes
```

```
kubectl resize --replicas=2 rc my-nginx
```


```
kubectl expose rc my-nginx --port=80
```