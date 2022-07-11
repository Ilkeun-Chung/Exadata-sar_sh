# Exadata sar.sh, Oracle Korea internal

#### 이 툴은 한국오라클 ES팀이 인터널로 제공하는 sar.sh를 사용하는 경우에 사용할 수 있습니다.

1. sar.sh version : 2.3.1을 바탕으로 개발되었습니다.

2. DB 서버 데이터가 아래와 같은 값을 내주면 사용이 가능합니다.
 2.1 노드 hostname에 db가 포함됨
 2.2 매트릭 수 및 위치
* Node      :       CPU Usage (%)      |    Memory(%)  |Ethernet MB/sec & packet cnt| infini(TCP:MB, RDS:MB, Total:MB)
* Node      : user  sys wait  idle runq| used real swap|rv size&packet|tr size&packt| tcp_rv tcp_tr rds_rv rds_tr  tot_rv  tot_tr
krx8adbadm03:  0.6  0.5  0.0  98.8    0| 43.6 32.8  0.0|    0.0     25    0.0     11|    0.0    0.0    0.1    0.1     1.5     3.3


3. 스토리지 서버 데이터가 아래와 같은 값을 내주면 사용이 가능합니다.
 3.1 노드 hostname에 cel가 포함됨
 3.1.1 hostname이 다를 경우 식별할 수 있는 값을 logstash_xx.conf
 3.2 매트릭 수 및 위치
