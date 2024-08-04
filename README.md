## Installing k3s on centos 

### Install Script[​](https://docs.k3s.io/quick-start#install-script "Direct link to Install Script")

K3s provides an installation script that is a convenient way to install it as a service on systemd or openrc based systems. This script is available at  [https://get.k3s.io](https://get.k3s.io/). To install K3s using this method, just run:

```
curl -sfL https://get.k3s.io | sh -
```

After running this installation:

-   The K3s service will be configured to automatically restart after node reboots or if the process crashes or is killed
-   Additional utilities will be installed, including  `kubectl`,  `crictl`,  `ctr`,  `k3s-killall.sh`, and  `k3s-uninstall.sh`
-   A  [kubeconfig](https://kubernetes.io/docs/concepts/configuration/organize-cluster-access-kubeconfig/)  file will be written to  `/etc/rancher/k3s/k3s.yaml`  and the kubectl installed by K3s will automatically use it

### Manual Configuration after installation
- Add **/usr/local/bin** to your PATH if it is missing:
	```
	export PATH=$PATH:/usr/local/bin
	```
- Make this change permanent by adding it to your .bashrc or .bash_profile:
	```
	echo 'export PATH=$PATH:/usr/local/bin' >> ~/.bashrc
	source ~/.bashrc
	```
- Set the **KUBECONFIG** environment variable:
	```
	echo 'export KUBECONFIG=/etc/rancher/k3s/k3s.yaml' >> ~/.bashrc
	source ~/.bashrc
	```
