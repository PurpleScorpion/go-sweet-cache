# sweet-cache

# 特别说明
本项目是在 [github.com/patrickmn/go-cache] 项目上修改的，只修改了部分代码, 增加使用便捷性
更多使用方法请参考 [github.com/patrickmn/go-cache]

# 新的使用方式
1. 引入依赖 go get github.com/PurpleScorpion/go-sweet-cache
2. 导包 import cache "github.com/PurpleScorpion/go-sweet-cache"
3. 创建缓存对象 cache.New(cache.NoExpiration, cache.NoExpiration)
```text
注: 该cache.New尽量在程序启动时创建, init的优先级尽量高, 建议只在main.go中使用init, 其他文件尽量不要使用init
具体的使用请参考[https://github.com/PurpleScorpion/go-sweet]
警告: cache.New仅可使用一次, 多次使用可能会导致获取不到之前的缓存数据
```
4. 使用案例
```text
[yaml包下进行初始化并向缓存中添加数据]
cache.New(cache.NoExpiration, cache.NoExpiration)
cache.SweetCache.Set("ymlConf", conf1, cache.NoExpiration)

[service包下直接获取缓存数据]
val, err := cache.SweetCache.Get("ymlConf")
```
            