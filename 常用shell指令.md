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
tar -czvf zikui.tar.gz dist
# 推送到服务器
scp zikui.tar.gz root@119.23.62.197:/root/temp
# 登录远程服务器
ssh root@119.23.62.197
# 解压包
tar -xzvf zikui.tar.gz
# 移除页面内容
rm -rf /usr/local/nginx/html/zikui/*
# 复制内容到到nginx目录
mv ~/dist/* /usr/local/nginx/html/zikui/
```