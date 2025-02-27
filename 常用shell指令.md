##### maven
```shell
mvn clean package -U -Dmaven.test.skip=true
```

##### 远程服务器
```
-- 复制到远程服务器
scp -p admin/target/zikui.war root@119.23.62.197:/usr/local/tomcat/webapps  
```

##### 参考脚本
```shell
# 执行脚本 h5

# build项目
cnpm run build
# 打包文件
tar -czvf fangxiao.tar.gz dist
# 推送到服务器
scp fangxiao.tar.gz root@120.27.137.50:~
# 登录远程服务器
ssh root@120.27.137.50
# 解压包
tar -xzvf fangxiao.tar.gz
# 移除页面内容
rm -rf /usr/local/nginx/html/fangxiao.gzzps.fun/*
# 复制内容到到nginx目录
mv ~/dist/* /usr/local/nginx/html/fangxiao.gzzps.fun/
```