## Node_redis example for Tile38

[node_redis project page](https://github.com/NodeRedis/node_redis)

All Tile38 commands should be sent using the `client.send_command(name, args, callback)` function.

Install the node_redis library:

```
npm install redis
```

Complete example:

```javascript
var redis = require("redis")
var client = redis.createClient(9851, "localhost")

client.send_command(
	"SET", ["fleet", "truck1", "POINT", "33", "-115"], 
	function(err, reply){
		if (err){
			// ERROR
		}else{
			console.log(reply)
			// OK
		}
	}
)

client.send_command(
	"GET", ["fleet", "truck1"],
	function(err, reply){
		if (err){
			// ERROR
		}else{
			console.log(reply)
			// {"type":"Point","coordinates":[-115,33]}
		}
	}
)

```