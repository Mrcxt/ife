- 将一段数字从右到左每隔三位插入一个逗号。（视频网站优酷土豆，观看点赞人数的显示方式）

```JavaScript
        (function() {
            function spliceComma(string) {
                var arr = string.split('').reverse();
                var index = 0;
                for (var i = 0; i < arr.length; i++) {
                    index++;
                    if (index % 3 == 0) {
                        arr.splice(i + 1, 0, ',');
                        i++;
                    }
                }
                return arr.reverse().join('');
            }
            console.log(spliceComma("1000000000"))
        })()
```