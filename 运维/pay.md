##### 查看df短信
```shell
grep -C 0 '代付验证码' /data/logs/ngcash/catalina.out | grep -C 0 '284864'
```