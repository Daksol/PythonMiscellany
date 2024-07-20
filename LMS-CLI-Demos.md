# LMS CLI Python Code Examples

## Make sure it works - serverstatus


```python
from lms_jsonrpc_module import lms_jsonrpc
myLMS = ('192.168.5.75', '9005')

print(lms_jsonrpc(lms=myLMS, cmdlist=['serverstatus']))
```

    {'lastscan': '1721448044', 'version': '9.0.0', 'uuid': '9caf975e-f502-47db-ad3e-135ab16a86fa', 'ip': '192.168.5.75', 'httpport': '9005', 'info total albums': 589, 'info total artists': 623, 'info total genres': 108, 'info total songs': 9615, 'info total duration': 7477002.51200002, 'player count': 4, 'other player count': 0}
    

## Using player command


```python
from lms_jsonrpc_module import lms_jsonrpc
myLMS = ('192.168.5.75', '9005')

playercount = lms_jsonrpc(lms=myLMS, cmdlist=['player', 'count', '?'])['_count']
print(f'Player count:{playercount}')

for p_index in range(playercount):
    p_id = lms_jsonrpc(lms=myLMS, cmdlist=['player', 'id',p_index, '?'])['_id']
    p_name = lms_jsonrpc(lms=myLMS, cmdlist=['player', 'name',p_index, '?'])['_name']
    print(p_index, p_id, p_name)
```

    Player count:4
    0 00:04:20:2a:e0:74 Runcible Red
    1 a0:ce:c8:ce:a1:3b SLX-Local
    2 00:04:20:2a:c8:20 Scarlet Study
    3 00:04:20:28:c7:f1 Stalking Horse
    


```python

```
