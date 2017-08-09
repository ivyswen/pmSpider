# pmSpider
<p>定时从<a href="https://www.aqistudy.cn/">aqistudy</a>抓取空气质量数据</p>
<p>造福大气科研工作者[并不简单]</p>

### 文件目录

<pre>
|---common
|-----userAgents.json
|---cookieSetter.js
|---databaseUtil.js
|---getData.js
|---getServerData.js
|---index.js
|---package.json
|---raw.js
|---raw.txt
|---sendPost.js
</pre>

### 文件功能介绍

#### `index.js`
启动入口文件，开启定时任务，每小时抓取一次，并输出相关信息

#### `getData.js`
通过对网站进行分析，设置cookie，绑定城市信息，调起  `getServerData.js` 

#### `getServerData.js`
对请求参数进行加密，对返回参数进行解密，得到`json`数据串

#### `databaseUtil.js`
将获取到的数据保存到`mongodb`中，方便后续处理

#### `raw.js&&raw.txt`
将需要拉取的城市整理为一个数组，在启动时调用

#### `cookieSetter.js`
网站`cookie`的生成器，避免`cookie`过期失效，可以设置为定期更新

#### `userAgents.json`
防止爬虫被墙，储备的`userAgent`
但是目前没有发现该网站有对`ua`进行识别，后期可做成定期更换


## TODOS
<ul>
  <li>增加容错机制，在遇到异常时保证程序可以自动选择解决方案</li>
  <li>对保存在数据库中的数据进行定时处理，输出为excel文件</li>
  <li>通过echart等工具，将数据可视化</li>
</ul>


## 联系作者

carlzzzz@163.com
yuancheng.yuan@qunar.com
http://carlz.top/



