probelm 1:握手协议描述
当两节点建立连接，需要先互相确认再进行通讯
1.Local和Remote节点互相发送version信息
2.收到version信息后互相发送verack消息，收到verack后握手成功开始通讯
3.若存在inv消息则发送getdata消息，对方推送更新内容
4.若当前区块头高度小于目标区块头高度则发送getheaders消息
5.若当前区块高度小于目标区块高度则发送getblocks消息


problem 2：对比以太坊gossip协议
gossip协议
优点：
组成网络的节点都是对等的，网络中即使有的节点因宕机而重启，或有新节点加入，但经过一段时间后，这些节点的状态也会与其他节点达成一致，
Gossip具有分布式容错的优点，是一个带冗余的容错算法和最终一致性算法。
缺点：
冗余通信会对网路带宽、CPU资源造成很大的负载，而这些负载又受限于通信频率，该频率又影响着算法收敛的速度。

NEO
优点：
延迟小，同步快，由共识节点治理。
缺点：
若丢失已同步的区块数据无法达成最终一致。
