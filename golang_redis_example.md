## golang_redis example for Tile38

[golang_redis project page](https://github.com/go-redis/redis)

All Tile38 commands should  use  `redis.NewStringCmd(...args)` to orgnize parameters, then, use `Process()` to request result ,and get result by using `Result()`.

[Install the golang_redis library](https://github.com/go-redis/redis):

```
go get gopkg.in/redis.v5
```

Complete example:

```go
import "gopkg.in/redis.v5"
func testTile38(){
	client := redis.NewClient(&redis.Options{
		Addr: "127.0.0.1:9851",
	})
	cmd := redis.NewStringCmd("SET", "fleet", "truck44", "POINT", 33.32, 115.423)
	client.Process(cmd)
	v, _ := cmd.Result()
	log.Println(v)
	cmd1 := redis.NewStringCmd("GET", "fleet", "truck44")
	client.Process(cmd1)
	v1, _ := cmd1.Result()
	log.Println(v1)
}

func main(){
  testTile38()
}
```