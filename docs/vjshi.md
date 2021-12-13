Hook
useSearchHistory --- 拿，存， 删除cookies的值
const { histories, add, clear } = useSearchHistory('SH')

Component
<CardList col="4">{children}</CardList>  --- 实现均分效果（左右无padding）


1.中间层
vjh/vjs:新接口，放vedios_v2
pc：老接口，放vedio
2.基础包
新接口，放videos
老接口：videosOld
3.路由
10338--开发服
18378--测试服

基础包打包注入开发项目：sudo ./local-build.sh

rebase合并
git checkout -b develop origin/develop
git pull origin develop
git checkout dev 
git rebase develop   
git checkout develop
git rebase dev  
it checkout dev 
git push origin dev  (-f)

git rebase -i HEAD~4
￼
修改第2-4行的第一个单词pick为squash
保存退出： “:wq”
Git push origin dev -f


页面跳转：
站内：react.Router
站外：余航Links
外网： ChackraUI 的Link

中间层：koa-proxy-server:
Export NODE_ENV=development—测试服
Export NODE_ENV=local—开发服

 node ./index.js

Token：90days—2021.11.17：（Github自己的）
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

