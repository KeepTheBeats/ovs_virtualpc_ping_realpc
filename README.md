# OVS实现虚拟机与外部主机通信

---

#### 这个实验是“锐捷SDN培训福州专场”中的，我在做了这个实验之后觉得原版实验中有一些我不是非常理解的操作和设置，所以我做了一些修改。

#### 如：我不理解PORT2是否有必要，在ppt中也没有讲PORT2与ETH(X)相连。我也不理解宿主机的ip地址有没有必要设置。

#### 我把原版实验的ppt也上传了，是“SDN部署实现虚拟机与外部主机通信.pptx”这个文件。


---

- 我把实验中宿主机外部通过锐捷交换机的那部分去掉了，重点在OVS部分。
- 配置的各种截图都已上传。

1. 实验开始前先在宿主机上sudo mn -c。宿主机装了mininet，这个指令可以清除掉所有ovs的配置。
2. 在本机建立ovs网桥：sudo ovs-vsctl add-br ovs。
3. 将eth(x)桥接到ovs网桥上： sudo ovs-vsctl add-port ovs eth(x)。
4. 创建ovs虚拟机网桥新的网卡port1：
    * sudo ip tuntap add mode tap port1
	* sudo ip link set port1 up
	* sudo ovs-vsctl add-port ovs port1
5. 查看陈列出ovs交换机接口信息：sudo ovs-vsctl list-ports ovs。
6. 将虚拟机桥接到port1上，见“network_bridge_port1.png”。
7. 将虚拟机和外部pc的ip地址设置为同一网段，即可ping通。
