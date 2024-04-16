# CharacterCountHadoop

## Steps to run
- git clone https://github.com/big-data-europe/docker-hadoop
- cd docker-hadoop
- docker-compose up -d
- First go into the folder CharacterCountHadoop
- docker cp charcount.jar namenode:/
- docker cp data namenode:/
- docker exec -it namenode /bin/bash
- hdfs dfs -mkdir /user/root/charcount
- hdfs dfs -mkdir /user/root/charcount/input
- hdfs dfs -put data/* /user/root/input/charcount/input/
- hadoop jar charcount.jar org.myorg.CharacterCount charcount/input charcount/output
- hdfs dfs -cat /user/root/charcount/output/*
