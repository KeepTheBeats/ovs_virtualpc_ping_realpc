# OVSʵ����������ⲿ����ͨ��

---

#### ���ʵ���ǡ����SDN��ѵ����ר�����еģ������������ʵ��֮�����ԭ��ʵ������һЩ�Ҳ��Ƿǳ����Ĳ��������ã�����������һЩ�޸ġ�

#### �磺�Ҳ����PORT2�Ƿ��б�Ҫ����ppt��Ҳû�н�PORT2��ETH(X)��������Ҳ�������������ip��ַ��û�б�Ҫ���á�

#### �Ұ�ԭ��ʵ���pptҲ�ϴ��ˣ��ǡ�SDN����ʵ����������ⲿ����ͨ��.pptx������ļ���


---

- �Ұ�ʵ�����������ⲿͨ����ݽ��������ǲ���ȥ���ˣ��ص���OVS���֡�
- ���õĸ��ֽ�ͼ�����ϴ���

1. ʵ�鿪ʼǰ������������sudo mn -c��������װ��mininet�����ָ��������������ovs�����á�
2. �ڱ�������ovs���ţ�sudo ovs-vsctl add-br ovs��
3. ��eth(x)�Žӵ�ovs�����ϣ� sudo ovs-vsctl add-port ovs eth(x)��
4. ����ovs����������µ�����port1��
    * sudo ip tuntap add mode tap port1
	* sudo ip link set port1 up
	* sudo ovs-vsctl add-port ovs port1
5. �鿴���г�ovs�������ӿ���Ϣ��sudo ovs-vsctl list-ports ovs��
6. ��������Žӵ�port1�ϣ�����network_bridge_port1.png����
7. ����������ⲿpc��ip��ַ����Ϊͬһ���Σ�����pingͨ��
