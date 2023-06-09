# gf - Generic Functions For Go 1.18+

* 注意：部分方法仅可在Go版本大于等于1.18时使用！

### 什么是gf包？

* gf包 是一个容纳一些比较常用的函数的库，主要用于简化 Go 编程。

### 使用方法

```shell
go get -u github.com/tiancheng92/gf
```

### gf包方法详解

#### 字符串相关

| 函数名              | 描述                            |
|:-----------------|-------------------------------|
| StringJoin       | 字符串拼接（使用strings.Builder以提升性能） |
| StringToBytes    | 字符串转[]byte                    |
| BytesToString    | []byte转字符串                    |
| StringCreateGzip | 对字符串进行gzip压缩                  |
| StringParseGzip  | 对gzip压缩后的字符串进行解压              |

* Code：[string.go](https://github.com/tiancheng92/gf/blob/main/string.go)
* Test：[string_test.go](https://github.com/tiancheng92/gf/blob/main/string_test.go)
* Example：[example/main.go](https://github.com/tiancheng92/gf/blob/main/example/main.go)

#### 浮点数相关

* 注意：以下方法均使用泛型实现，可以用于任意底层类型为float64或float32的类型

| 函数名        | 描述           |
|:-----------|--------------|
| FloatRound | 保留浮点数指定位数的小数 |

* Code：[float.go](https://github.com/tiancheng92/gf/blob/main/float.go)
* Test：[float_test.go](https://github.com/tiancheng92/gf/blob/main/float_test.go)
* Example：[example/main.go](https://github.com/tiancheng92/gf/blob/main/example/main.go)

#### 切片相关

* 注意：以下方法均使用泛型实现，可以用于任意类型的数组。

| 函数名                | 描述                                                      |
|:-------------------|---------------------------------------------------------|
| ArrayDeduplicate   | 数组去重                                                    |
| ArrayEqual         | 数组比较                                                    |
| ArrayContains      | 查询数组是否包含指定元素                                            |
| ArrayIntersect     | 两个数组取交集                                                 |
| ArrayUnion         | 两个数组取并集                                                 |
| ArrayDifference    | 两个数组取差集                                                 |
| ArrayFilter        | 使用函数对数组进行过滤（过滤函数签名为：func(any) bool）                     |
| ArrayReverse       | 数组反转                                                    |
| ArrayBubbleSort    | 数组进行冒泡排序（仅需实现less方法：func (array []any, i, j int) bool）  |
| ArrayInsertionSort | 数组进行插入排序（仅需实现less方法：func(array []any, i, j int) bool）   |
| ArrayHeapSort      | 数组进行堆排序（仅需实现less方法：func(array []any, i, j int) bool）    |
| ArrayQuickSort     | 数组进行快速排序（仅需实现less方法：func(array []any, i, j int) bool）   |
| ArraySort          | 数组进行go原生排序（仅需实现less方法：func(array []any, i, j int) bool） |
| ArraySplit         | 把一维数组按步长切分为二维数组                                         |

* Code：[array.go](https://github.com/tiancheng92/gf/blob/main/array.go)
* Test：[array_test.go](https://github.com/tiancheng92/gf/blob/main/array_test.go)
* Example：[example/main.go](https://github.com/tiancheng92/gf/blob/main/example/main.go)

#### URL相关

| 函数名       | 描述                                    |
|:----------|---------------------------------------|
| UrlFormat | 将url格式化（会进行URL合规性检测、冗余字符删除、query参数排序） |

* Code：[url.go](https://github.com/tiancheng92/gf/blob/main/url.go)
* Test：[url_test.go](https://github.com/tiancheng92/gf/blob/main/url_test.go)
* Example：[example/main.go](https://github.com/tiancheng92/gf/blob/main/example/main.go)

#### Percentile百分位数相关

| 函数名        | 描述     |
|:-----------|--------|
| Percentile | 获取百分位数 |

* Code：[percentile.go](https://github.com/tiancheng92/gf/blob/main/percentile.go)
* Test：[percentile_test.go](https://github.com/tiancheng92/gf/blob/main/percentile_test.go)
* Example：[example/main.go](https://github.com/tiancheng92/gf/blob/main/example/main.go)

#### Period Time 周期时间相关

| 函数名           | 描述       |
|:--------------|----------|
| NewPeriodTime | 创建周期时间对象 |
| Append        | 添加时间段    |
| Union         | 多个时间段取并集 |
| Intersect     | 多个时间段取交集 |
| Duration      | 获取总时长    |

* Code：[period_time.go](https://github.com/tiancheng92/gf/blob/main/period_time.go)
* Test：[period_time_test.go](https://github.com/tiancheng92/gf/blob/main/period_time_test.go)
* Example：[example/main.go](https://github.com/tiancheng92/gf/blob/main/example/main.go)

#### goroutine 相关
| 函数名           | 描述       |
|:--------------|----------|
| Go | 创建recover的go程 |
* Code: [safe_goroutine.go](https://githk.azurlane.jp:8888/go-kit/gf/blob/main/safe_goroutine.go)
* Test: [safe_goroutine_test.go](https://githk.azurlane.jp:8888/go-kit/gf/blob/main/safe_goroutine_test.go)