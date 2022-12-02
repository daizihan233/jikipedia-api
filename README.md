## **_jikipedia_**
### Dev - 开发时
> 这个检测报告往往指在开发者电脑上开发时（未发布或自用但未发布）的安全性
> 也意味着下一次上传是 **可能的** 安全性（因为代码可能会因为一些原因有变动，请以生产时为准）

[![OSCS Status](https://www.oscs1024.com/platform/badge/daizihan233/jikipedia-api.git.svg?size=large)](https://www.murphysec.com/dr/Th9ywEPBKMOIL5T8ap)

### Release - 生产时
> 这个版本是你在 Pypi 上看见的版本，也是你使用的版本

[![OSCS Status](https://www.oscs1024.com/platform/badge/daizihan233/jikipedia.svg?size=large)](https://www.murphysec.com/dr/FON52roiQ5ZNBOITkF)

### “查网络流行语，就上小鸡词典！” &nbsp;——小鸡词典
注意：该项目还在开发完善中，有Bug欢迎反馈<br>
注意：请一定要保持更新，否则会导致某些功能失效
### 相关页面导航栏
[小鸡词典 Jikipedia](https://jikipedia.com/) <br>
[作者主页 @Bug鸡](https://jikipedia.com/definitions/user/281250396) <br>
[协助开发 @三滑稽甲苯](https://jikipedia.com/definitions/user/824221130) <br>
[Github项目 Jikipedia](https://github.com/daizihan233/jikipedia) <br>

### _有什么用？做了什么？还要做什么？_
#### 互动类
- [x] 签到
- [x] 补签
- [ ] 收藏
- [x] 点赞 / 取消点赞
- [x] 评论 / 回复
- [ ] 关注 / 取消关注
#### 数据类
- [x] 生成XID
- [x] 加密XID
- [x] Token获取
- [ ] 被阅读、点赞的数据
- [ ] 个人信息
- [ ] 关注（者）
- [ ] 粉丝（者）
- [ ] 词条内容
- [ ] 词条编写者
- [x] 搜索栏的推荐
- [ ] 获取昵称
- [ ] 获取头像
- [ ] 获取签名
#### 创作类
- [ ] 创建词条
- [ ] 创建杂谈
#### 活动类
- [x] 恶魔鸡翻译器
- [x] 我们的维权
- [x] 黄狗JK
### 食用教程
#### 安装
```
pip install jikipedia
```
****
#### import
```
import jikipedia
```
****
#### 初始化
```
jiki = jikipedia.Jikipedia(phone='12345678901', password='123456')
```
参数：<br>

| 参数名称     | 参数类型 | 参数释义 |
|----------|------|------|
| phone    | str  | 手机号  |
| password | str  | 密码   |

返回：<br>

| 返回值名称 | 返回值类型 | 可能的值 | 返回值释义 |
|-------|-------|------|-------|
| -     | -     | -    | -     |
****
#### 生成明文XID
_感谢 [@三滑稽甲苯](https://jikipedia.com/definitions/user/824221130) 协助逆向_
```
xid = generate_plaintext_xid()
```
参数：<br>

| 参数名称 | 参数类型 | 参数释义 |
|------|------|------|
| -    | -    | -    |

返回：<br>

| 返回值名称 | 返回值类型 | 可能的值 | 返回值释义 |
|-------|-------|------|-------|
| xid   | str   | -    | 明文xid |
****
#### 生成密文XID
```
xid = encode_xid()
xid = encode_xid(xid)
```
参数：<br>

| 参数名称 | 参数类型 | 参数释义                 |
|------|------|----------------------|
| XID  | str  | 需要明文XID，可选，不填则默认随机生成 |

返回：<br>

| 返回值名称 | 返回值类型 | 可能的值 | 返回值释义 |
|-------|-------|------|-------|
| xid   | str   | -    | 加密xid |
****
#### Token获取
```
token = jiki.get_token()
```
参数：<br>

| 参数名称 | 参数类型 | 参数释义 |
|------|------|------|
| -    | -    | -    |

返回：<br>

| 返回值名称 | 返回值类型 | 可能的值 | 返回值释义    |
|-------|-------|------|----------|
| token | str   | -    | 获取的Token |

**注意：脚本会使登录信息失效**<br>
<br>
**解决方法1：服务器也是会累的，把频率调低，让服务器休息一会儿吧！**<br>
<br>
**解决方法2：用手机APP**
****
#### 恶魔鸡翻译器
```
emoji(text)
```
参数：<br>

| 参数名称 | 参数类型 | 参数释义   |
|------|------|--------|
| text | str  | 待翻译的文本 |

返回：<br>

| 返回值名称 | 返回值类型 | 可能的值 | 返回值释义  |
|-------|-------|------|--------|
| text  | str   | -    | 翻译后的结果 |
****
#### 搜索栏的推荐
```
get_search_recommend()
```
**_注：也就是排行榜TOP1的词条_**

参数：<br>

| 参数名称 | 参数类型 | 参数释义 |
|------|------|------|
| -    | -    | -    |

返回：<br>

| 参数名称        | 参数类型 | 参数释义            |
|-------------|------|-----------------|
| phrase      | str  | 词条名             |
| placeholder | str  | 搜索栏在没有点击时显示的的文案 |
****
#### 点赞 / 取消点赞
```
jiki.like(id_, status)
```
参数：<br>

| 参数名称   | 参数类型 | 参数释义                       |
|--------|------|----------------------------|
| id_    | int  | 词条id                       |
| status | bool | True为点赞，False为取消，可选，不填默认点赞 |

返回：<br>

| 返回值名称   | 返回值类型 | 可能的值        | 返回值释义   |
|---------|-------|-------------|---------|
| HTTP状态码 | int   | 2xx/4xx/5xx | HTTP状态码 |
****
#### 签到
_感谢 [@三滑稽甲苯](https://jikipedia.com/definitions/user/824221130) 提供的代码_<br>
_此功能**基于** [@三滑稽甲苯](https://jikipedia.com/definitions/user/824221130) 提供的代码**二改**而来_

```
jiki.sign()
```
参数：<br>

| 参数名称 | 参数类型 | 参数释义 |
|------|------|------|
| -    | -    | -    |

返回：<br>


| 返回值名称  | 返回值类型 | 可能的值       | 返回值释义            |
|--------|-------|------------|------------------|
| status | bool  | True/False | True为成功，False为失败 |
****
#### 我们的维权
```
jiki.gather_event_hope(count)
```
参数：<br>

| 参数名称  | 参数类型 | 参数释义                        |
|-------|------|-----------------------------|
| count | int  | 要刷多少，可选，不填默认2000（实际可能是1024） |

**注意：实测上限在1024左右，但超过1024不会报错，建议填写区间为1-2000以内的整数**

返回：<br>

| 返回值名称 | 返回值类型 | 可能的值 | 返回值释义                                    |
|-------|-------|------|------------------------------------------|
| count | int   | -    | 所有人一共刷了多少，如果返回值为0则代表超出上限，要等一会再来（大概2-4小时） |


****
#### 补签
```
jiki.ssign(year, mouth, day)
```
参数：<br>

| 参数名称  | 参数类型 | 参数释义 |
|-------|------|------|
| year  | int  | 哪一年？ |
| mouth | int  | 哪一月？ |
| day   | int  | 哪一天？ |

返回：<br>

| 返回值名称   | 返回值类型 | 可能的值            | 返回值释义      |
|---------|-------|-----------------|------------|
| HTTP状态码 | int   | 200（成功）/403（失败） | 返回的HTTP状态码 |
****
#### 评论 / 回复
```
jiki.comment(definition, text, reply)
```
参数：<br>

| 参数名称       | 参数类型 | 参数释义       |
|------------|------|------------|
| definition | int  | 词条id       |
| text       | str  | 评论内容       |
| reply      | int  | 选填，回复评论的id |

返回：<br>

| 返回值名称      | 返回值类型 | 可能的值 | 返回值释义          |
|------------|-------|------|----------------|
| API返回的json | dict  | -    | 可以自己研究，有时间就写文档 |
****
#### 黄狗JK
~~方便大家观察~~<br>
_**不要看了，请跳过这个功能，因为活动已经结束了，API暴毙时间未知**_
_**目前新版本测试时发现此函数出现异常，原因未知，请自测**_
```
jiki.jk()
```
参数：<br>

| 参数名称 | 参数类型 | 参数释义 |
|------|------|------|
| -    | -    | -    |

返回：<br>

| 返回值名称 | 返回值类型 | 可能的值 | 返回值释义      |
|-------|-------|------|------------|
| count | int   | -    | 这个月新增多少词条？ |

[//]: # (**_~~为了让大家更好地观察，这里放出示例代码~~_**<br>)

[//]: # (运行前请保证装有```Python```，并安装了```time``` ```jikipedia``` ```win10toast```，保证系统为```Windows 10及以上```)

[//]: # (```)

[//]: # (import time)

[//]: # (import jikipedia)

[//]: # (from win10toast import ToastNotifier)

[//]: # (# 初始化)

[//]: # (jiki = jikipedia.Jikipedia&#40;phone='12345678901', password='password'&#41;  # 这里替换成你的手机号和密码)

[//]: # (count_old = count = jiki.jk&#40;&#41;  # 初始化计数器)

[//]: # (print&#40;'Init: '&#41;  # 输出调试信息)

[//]: # (print&#40;'count =', count&#41;  # 输出调试信息)

[//]: # (print&#40;'count_old =', count_old&#41;  # 输出调试信息)

[//]: # (toaster = ToastNotifier&#40;&#41;  # 初始化消息提示器)

[//]: # (toaster.show_toast&#40;'Jikipedia - 黄狗JK任务监视器', 'Jikipedia is running...', duration=10&#41;  # 显示消息提示器)

[//]: # (# 开始监控)

[//]: # (while True:  # 死循环)

[//]: # (    count = jiki.jk&#40;&#41;  # 获取当前数量)

[//]: # (    print&#40;'count =', count&#41;  # 输出调试信息)

[//]: # (    if count != count_old:  # 如果当前数量不等于上一次检测的数量)

[//]: # (        print&#40;'count&#40;{}&#41; != count_old&#40;{}&#41;'.format&#40;count, count_old&#41;&#41;  # 输出调试信息)

[//]: # (        toaster.show_toast&#40;'Jikipedia - 黄狗JK任务监视器', 'Now: {}\n')

[//]: # (                                                    'Old: {}'.format&#40;count, count_old&#41;, duration=10&#41;  # 显示消息提示器)

[//]: # (        count_old = count  # 更新上一次检测的数量)

[//]: # (    time.sleep&#40;600&#41;  # 每10分钟（600秒）检测一次，秒为单位，建议把数字调高，否则会经常登录失效)

[//]: # ()
[//]: # (```)
****
#### 获取热搜
```
jiki.get_hot()
```
参数：<br>

| 参数名称 | 参数类型 | 参数释义 |
|------|------|------|
| -    | -    | -    |

返回：<br>

| 返回值名称 | 返回值类型 | 可能的值 | 返回值释义        |
|-------|-------|------|--------------|
| -     | dict  | -    | API返回值，过长不赘述 |