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
    r = redis.Redis(host='127.0.0.1', port=9851)
    # insert data
    result = r.execute_command('SET fleet truck2 POINT 33.32 115.423')
    # print result
    print result
    # get data
    print r.execute_command('GET fleet truck2')

if __name__ == '__main__':
    test_tile38()
```