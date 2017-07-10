- 判断一个字符串中出现次数最多的字符，统计这个次数

> 解析：此题有多种解决思路。**第一种**思路是通过charAt()对比每个字符是否相同，然后通过一个对象来存储每个字符出现的次数。**第二种**思路大同小异，通过indexOf对比每个字符第一次出现的位置是否与当前位置相同，不相同则代表至少出现过一次。同样是通过一个对象来存储。

下面是第二种思路的解决方案：
```JavaScript
        (function() {
            function stringMax(string) {
                var json = {}; //新建一个对象用来存储每个字符出现的次数
                var length = string.length; //字符串长度
                for (var i = 0; i < length; i++) {
                    var index = string.indexOf(string[i]); //当前字符第一次出现的位置
                    if (index == i) {
                        json[string[i]] = 1; //如果相等，说明该字符第一次出现
                    } else {
                        json[string[i]]++; //否则，直接将该字符对应的值+1；
                    }
                }
                console.log(json); //每个字符出现的次数

                var str = ''; //出现最多的字符
                var num = 0; //出现最多的次数
                for (var i in json) {
                    if (json.hasOwnProperty(i)) {
                        if (json[i] > num) {
                            str = i;
                            num = json[i];
                        }
                    }
                }
                // 输出
                console.log('出现最多的字符：' + str + ',' + '出现的次数：' + num);
            }
            // 测试
            var a = 'asdfghjklhsdfghjsdfaassssaaaaaaaa'
            stringMax(a);
        })()
```