1. sar.sh version : 2.3.1을 바탕으로 개발되었습니다.

2. DB 서버 데이터가 아래와 같은 값을 내주면 사용이 가능합니다.    
2.1 노드 hostname에 db가 포함됨    
2.2 매트릭 수 및 위치    
Node      :       CPU Usage (%)      |    Memory(%)  |Ethernet MB/sec & packet cnt| infini(TCP:MB, RDS:MB, Total:MB)    
Node      : user  sys wait  idle runq| used real swap|rv size&packet|tr size&packt| tcp_rv tcp_tr rds_rv rds_tr  tot_rv  tot_tr    
krx8adbadm03:  0.6  0.5  0.0  98.8    0| 43.6 32.8  0.0|    0.0     25    0.0     11|    0.0    0.0    0.1    0.1     1.5     3.3    

3. 스토리지 서버 데이터가 아래와 같은 값을 내주면 사용이 가능합니다.    
3.1 노드 hostname에 cel가 포함됨   
3.1.1 hostname이 다를 경우 식별할 수 있는 값을 Exadata-sar-xx_YYYYMMDD.conf 에서 수정   
3.2.1 매트릭 수 및 위치 - HC TYpe
Node       : Total |              Disk I/O (MB)             |             Flash I/O (MB)             | CPU |  Infini(MByte)    
MB/s       :   Sum |   Read  Write  Avg%  Max%     tps svctm|   Read  Write  Avg%  Max%     tps svctm|  pct| receive transfer    
krx8aceladm01:   63.5|   41.5   21.6   1.6  18.4    2686  0.29|    0.0    0.3   0.0   0.0      20  0.00|  4.1|     0.1      0.1    
3.2.2 매트릭 수 및 위치 - EF TYpe    
Node       : Total |             Flash I/O (MB)             | CPU |  Infini(MByte)    
MB/s       :   Sum |   Read  Write  Avg%  Max%     tps svctm|  pct| receive transfer    
krx8aceladm04:    0.3|    0.1    0.2   0.0   0.0      64  0.01|  5.0|     0.0      0.0    
