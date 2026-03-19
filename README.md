# 一键便捷式修改VPS的SSH端口脚本

主要用于Debian/Ubuntu系统。

### SSH端口修改脚本 (change_ssh_port.sh)

**功能描述**: 交互式修改SSH服务端口，自动备份配置、验证端口可用性、配置防火墙。

**主要特性**:
- ✅ 交互式端口选择，提供智能建议
- ✅ 自动检测端口冲突和占用
- ✅ 警告系统保留端口和常见服务端口
- ✅ 二次确认机制，防止误操作
- ✅ 自动备份配置文件
- ✅ 配置文件语法检查
- ✅ 自动配置防火墙规则（支持UFW和firewalld）
- ✅ 错误自动回滚
- ✅ 彩色界面输出

---

## 🚀 使用方法

### 方法1: 直接在线执行（推荐）

```bash
bash <(curl -Ls https://raw.githubusercontent.com/Null404-0/scripts/main/change_ssh_port.sh)
```

或使用 wget:

```bash
bash <(wget -qO- https://raw.githubusercontent.com/Null404-0/scripts/main/change_ssh_port.sh)
```

### 方法2: 下载后执行

```bash
# 下载脚本
curl -O https://raw.githubusercontent.com/Null404-0/scripts/main/change_ssh_port.sh

# 添加执行权限
chmod +x change_ssh_port.sh

# 运行脚本
sudo bash change_ssh_port.sh
```

---



## ⚠️ 重要提醒

### 修改SSH端口前必读

1. **不要关闭当前连接**: 修改完成后，先用新端口测试连接成功，再关闭旧连接
2. **云服务器安全组**: 如果使用阿里云/腾讯云/AWS等，需要在控制台的安全组中开放新端口
3. **防火墙配置**: 确保防火墙允许新端口的TCP连接
4. **备份配置**: 脚本会自动备份，但建议手动再备份一次


**❌ 避免端口**:
- `1-1023` - 系统保留端口
- `80, 443` - HTTP/HTTPS服务
- `3306` - MySQL数据库
- `6379` - Redis
- `8080, 8888` - 常见Web服务

