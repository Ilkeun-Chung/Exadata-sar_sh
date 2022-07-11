# Exadata sar.sh, Oracle Korea internal

#### 이 툴은 한국오라클 ES팀이 인터널로 제공하는 sar.sh를 사용하는 경우에 사용할 수 있습니다.

1. sar.sh version : 2.3.1을 바탕으로 개발되었습니다.

2. DB 서버 데이터가 아래와 같은 값을 내주면 사용이 가능합니다.    
2.1 노드 hostname에 db가 포함됨    
2.2 매트릭 수 및 위치    
![image](https://user-images.githubusercontent.com/97824573/178221225-16cbe295-164f-4fbb-8e95-1e0b473443e7.png)

3. 스토리지 서버 데이터가 아래와 같은 값을 내주면 사용이 가능합니다.    
3.1 노드 hostname에 cel가 포함됨   
3.1.1 hostname이 다를 경우 식별할 수 있는 값을 Exadata-sar-xx_YYYYMMDD.conf 에서 수정   
3.2.1 매트릭 수 및 위치 - HC TYpe     
![image](https://user-images.githubusercontent.com/97824573/178221332-f87f581a-9c1e-4df7-9bc6-1749a142eeff.png)
3.2.2 매트릭 수 및 위치 - EF TYpe    
![image](https://user-images.githubusercontent.com/97824573/178221391-c74f61a3-0155-491c-bd56-3a54c6e0c4c8.png)


4. filebeat.yml 주요 변경 부분
<pre>
filebeat.inputs:

- type: filestream
#- type: log

  #enabled: false
  enabled: true

  # Paths that should be crawled and fetched. Glob based paths.
  paths:
    - /root/sarlog/sar*log
    #- c:\programdata\elasticsearch\logs\*

  # Include lines. A list of regular expressions to match. It exports the lines that are
  # matching any regular expression from the list.
  include_lines: ['db', 'cel']


#output.elasticsearch:


output.logstash:
  # The Logstash hosts
  hosts: ["localhost:5044"]
</pre>
