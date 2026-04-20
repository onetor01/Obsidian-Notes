
```shell
# 查询服务的端口占用
PID=$(ps -ef | grep adh_server | grep -v auto | awk '{print $2}' | head -1) && ss -tlnp | grep "pid=$PID"

# 根据端口查服务
PID=$(ss -tlnp | grep 8007 | grep -oP 'pid=\K[0-9]+') && ps -ef | grep $PID
```