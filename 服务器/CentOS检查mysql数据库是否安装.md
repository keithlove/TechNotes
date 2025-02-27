在CentOS系统上，你可以通过以下步骤检查是否已安装MySQL数据库：

---

#### 方法1：检查安装的RPM包
**执行命令**：
```bash
rpm -qa | grep -E 'mysql|mariadb'
```

**结果说明**：
- 若输出包含 `mysql-server`、`mysql-community-server` 或 `mariadb-server` 等包名，则表示已安装。
- 若无输出或仅显示客户端工具（如 `mysql-client`），则可能未安装完整的MySQL服务端。

---

#### 方法2：检查MySQL服务状态
**执行命令**：
```bash
systemctl status mysqld mariadb
```

**结果说明**：
- 若显示 `active (running)`，表示MySQL/MariaDB已安装且正在运行。
- 若显示 `Unit mysqld.service could not be found.`，则可能未安装。

---

#### 方法3：查找MySQL数据目录
**执行命令**：
```bash
ls /var/lib/mysql
```

**结果说明**：
- 如果目录存在且包含数据库文件（如 `ibdata1`、`mysql` 子目录等），则可能已安装MySQL。

---

#### 方法4：尝试运行MySQL客户端
**执行命令**：
```bash
mysql --version
```

**结果说明**：
- 若输出类似 `mysql  Ver 8.0.26 for Linux on x86_64 (MySQL Community Server)`，说明已安装客户端（服务端可能也已安装）。
- 若提示 `command not found`，则未安装。

---

#### 常见情况说明
1. **CentOS默认使用MariaDB**  
   CentOS 7及以上版本可能预装MariaDB（MySQL分支），检查时需注意包名是否为 `mariadb-server`。

2. **已安装但未启动服务**  
   即使包已存在，若服务未启动，需手动启动：
   ```bash
   sudo systemctl start mysqld   # MySQL
   sudo systemctl start mariadb  # MariaDB
   ```

---

#### 结论判断
- **已安装**：若上述方法中任意一步明确显示MySQL/MariaDB服务端组件存在。
- **未安装**：若所有步骤均无明确服务端证据。

如果需要安装MySQL，可参考阿里云文档或通过官方Yum仓库配置。需要进一步帮助请告知！