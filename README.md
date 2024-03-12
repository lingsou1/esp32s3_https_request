## 文件的简介

1. baiduAccessTokenGet.cpp 

- 该文件用于获取使用百度短语音识别的token参数
- 使用https请求
- 获取这个token的百度文档详见 : [https://ai.baidu.com/ai-doc/REFERENCE/Ck3dwjhhu]

2. clockSet.cpp

- 该文件用于校对时间(应该是)
- HTTPS请求需要先校对时间

3. httpRequest.cpp

- 该文件用于翻译数据(中译英,可自行修改)
- 使用HTTP请求,对百度翻译的API进行请求,会返回翻译数据,对翻译数据进行JSON解析即可
- 同时该程序中使用了MD5加密,百度要求对输入参数进行MD5加密
- 百度翻译的详细内容见 : [https://fanyi-api.baidu.com/product/113]

4. httpsResquest.cpp

- 该文件用于请求获取"一言"数据(中文)
- "一言"的内容详见:[https://developer.hitokoto.cn/sentence/]

5. JSONParseData.cpp

- 该文件用于解析JSON数据
- 其中的代码都是在[https://arduinojson.org/v6/assistant/]生成的

6. md5_generate.cpp

- 该文件是用于对字符串进行MD5加密的,并输出加密后的数据

7. shortSpeechRecognize.cpp

- 该文件用于将pcm格式的语音文件通过API的使用输出为文字
- 使用的是百度短语音识别
- 我使用的是以RAW方式上传音频(格式是.pcm)
- 百度短语音识别的详细内容见:[https://cloud.baidu.com/doc/SPEECH/s/Vk38lxily]
- 同时这是使用的HTTP请求,自定义了请求头,请求体(需要转换的录音文件就放在请求体中的)


8. wifiSet.cpp

- 该文件用于设置需要连接的WiFi,自己需要修改其中的WiFi名称及密码才能链接WiFi
- 同时由于使用了 WiFiMulti.h 所以可以在wifi_multi_init()这个函数中自己添加几个需要的WiFi

## 小提示

1. 我的录音文件放在data文件夹下的,名称是 16K.pcm 这是百度提供的文件,你可以替换成自己的文件,但是需要是.pcm格式
2. 需要先将录音文件上传至闪存中去再下载程序
3. 我尝试自己修改分区表来使用flash,在platformio.ini中添加了 board_build.partitions = partition.csv,同时生成了partition.csv该文件,编译没问题,flash显示程序占用的flash也变大了,下载程序也没报错,但是打开串口没有任何数据输出,取消自己分区后,程序又是正常的了,嗯,很困惑,我又尝试修改分区表,还是一样的错误,等哪天放假在看看乐鑫的文档吧,现在就不改分区表了
4. 问题还挺多的,下次再改
