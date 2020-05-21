### axios 使用方法
**参数-默认配置**

配置文件路径： `./src/plugins/vue-axios.js`
```
axios.defaults.timeout = 120000 // 超时时间
axios.defaults.baseURL = './' // 请求前缀路径
axios.defaults.headers['Content-Type'] = 'application/json;charset=UTF-8' // 数据类型
```

**请求拦截-默认配置**
```
// 全部axios的请求都会默认增加以下配置参数
header:{
    X-Requested-With:'XMLHttpRequest',
    language:Language.getDefaultLanguage(), // localStroage[language] || 浏览器默认语言设置
    REQUEST_HEADER: 'binary-http-client-header',
    requestId: Math.random() ,//请求id（随机数）
    Authorization:'Bearer token',  // oauth2.0 标准token格式
    token: token // token字符串
}
```

**响应拦截-默认配置**
* 如果 `headers` 里 设置 `totalReturn = true`,则完全返回完整的请求数据，否则仅返回 `data` 字段
* 要求返回字段必须包含 success/data/message

**使用方法**

this.axios(config)
```
// 发送 POST 请求
axios({
  method: 'post',
  url: '/user/12345',
  data: {
    firstName: 'Fred',
    lastName: 'Flintstone'
  }
});
```
```
// 获取远端图片
axios({
  method:'get',
  url:'http://bit.ly/2mTM3nY',
  responseType:'stream'
})
  .then(function(response) {
  response.data.pipe(fs.createWriteStream('ada_lovelace.jpg'))
});
```
this.axios(url[,config])
```
// 发送 GET 请求（默认的方法）
axios('/user/12345');
```

axios 请求方法的别名
* this.axios.request(config)
* this.axios.get(url[, config])
* this.axios.delete(url[, config])
* this.axios.head(url[, config])
* this.axios.options(url[, config])
* this.axios.post(url[, data[, config]])
* this.axios.put(url[, data[, config]])
* this.axios.patch(url[, data[, config]])

axios 并发
* this.axios.all(iterable)
* this.axios.spread(callback)

> 更多详情请查看 [http://www.axios-js.com/zh-cn/](https://note.youdao.com/)