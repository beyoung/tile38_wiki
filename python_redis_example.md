## python_redis example for Tile38

[python_redis project page](https://github.com/andymccurdy/redis-py)

All Tile38 commands should be sent using the `client.execute_command(command)` function.

[Install the python_redis library](https://github.com/andymccurdy/redis-py):

```
pip install redis
```

Complete example:

```python
import redis
def test_tile38():
    client = redis.Redis(host='127.0.0.1', port=9851)
    # insert data
    result = client.execute_command('SET fleet truck POINT 33.32 115.423')
    # print result
    print result
    # get data
    print client.execute_command('GET fleet truck')

if __name__ == '__main__':
    test_tile38()
```
