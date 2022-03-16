## **_jikipedia_**
### “查网络流行语，就上小鸡词典！” &nbsp;——小鸡词典
注意：该项目还在开发完善中，有Bug欢迎反馈<br>
注意：请一定要保持更新，否则会导致某些功能失效
### 相关页面导航栏
[小鸡词典 Jikipedia](https://jikipedia.com/) <br>
[作者主页 @Bug鸡](https://jikipedia.com/definitions/user/281250396) <br>
[协助开发 @三滑稽甲苯](https://jikipedia.com/definitions/user/824221130) <br>
[Github项目 Jikipedia](https://github.com/daizihan233/jikipedia) <br>
[闲着蛋疼做的网站 www.hantools.top](https://www.hantools.top/) <br>

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
from jikipedia import Jikipedia
```
****
#### 初始化
```
jiki = Jikipedia(phone='12345678901', password='123456')
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
xid = jiki.generate_plaintext_xid()
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
xid = jiki.encode_xid()
xid = jiki.encode_xid(xid)
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

**注意：如果在异地（比如服务器上）挂脚本的话，那么你的机子上登录信息可能会失效**<br>
<br>
**解决方法1：服务器也是会累的，把频率调低，让服务器休息一会儿吧！**<br>
<br>
**解决方法2：用手机APP**
****
#### 恶魔鸡翻译器
```
jiki.emoji(text)
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
jiki.get_search_recommend()
```
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
jiki.like(id, status)
```
参数：<br>

| 参数名称   | 参数类型 | 参数释义                       |
|--------|------|----------------------------|
| id     | int  | 词条id                       |
| status | bool | True为点赞，False为取消，可选，不填默认点赞 |

返回：<br>

| 返回值名称   | 返回值类型 | 可能的值    | 返回值释义   |
|---------|-------|---------|---------|
| HTTP状态码 | int   | 200/... | HTTP状态码 |
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

| 返回值名称 | 返回值类型 | 可能的值 | 返回值释义                                     |
|-------|-------|------|-------------------------------------------|
| count | int   | -    | 所有人一共刷了多少，如果返回值为0则代表超出上上限，要等一会再来（大概2-4小时） |
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
~~方便大家观察~~
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

**_~~为了让大家更好的观察，这里放出示例代码~~_**<br>
运行前请保证装有```Python```，并安装了```time``` ```jikipedia``` ```win10toast```，保证系统为```Windows 10及以上```
```
import time
import jikipedia
from win10toast import ToastNotifier
# 初始化
jiki = jikipedia.Jikipedia(phone='12345678910', password='password')  # 这里替换成你的手机号和密码
count_old = count = jiki.jk()  # 初始化计数器
print('Init: ')  # 输出调试信息
print('count =', count)  # 输出调试信息
print('count_old =', count_old)  # 输出调试信息
toaster = ToastNotifier()  # 初始化消息提示器
toaster.show_toast('Jikipedia - 黄狗JK任务监视器', 'Jikipedia is running...', duration=10)  # 显示消息提示器
# 开始监控
while True:  # 死循环
    count = jiki.jk()  # 获取当前数量
    print('count =', count)  # 输出调试信息
    if count != count_old:  # 如果当前数量不等于上一次检测的数量
        print('count({}) != count_old({})'.format(count, count_old))  # 输出调试信息
        count_old = count  # 更新上一次检测的数量
        toaster.show_toast('Jikipedia - 黄狗JK任务监视器', 'Now: {}\n'
                                                    'Old: {}'.format(count, count_old), duration=10)  # 显示消息提示器
    time.sleep(600)  # 每10分钟（600秒）检测一次，秒为单位，建议把数字调高，否则会经常登录失效

```
****
