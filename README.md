# cauc_csa



CAUC Cyber Security Association's Website

在我那死去但被我尝试救活的前端记忆和ChatGPT的帮助下，一直拖到现在的社团主页还是初步完成了。

### **项目简介**

这是 **中国民航大学网络空间安全协会 (CAUC Cyber Security Association)** 的官方网站项目，旨在为协会提供一个展示平台，传递我们的技术实力与团队文化。

没戳，页面是个纯静态站点，没有复杂的后端逻辑，甚至编写者懒得分离 CSS 文件。通过 Vue.js 的动态渲染能力，不仅让内容的管理和扩展变得更加方便，也为未来升级交互体验和添加功能预留了空间。

### **部署方法**（虽然觉得大家应该会才对，但是谁不是这么过来的呢）

以下过程仅为了照顾配置很不熟悉的师傅，其中路径和配置，包括使用的服务都可按照自己习惯来，此处使用apache2服务搭建。

1. **克隆项目到服务器**：

使用以下命令将项目克隆到服务器的指定目录：

```bash
git clone https://github.com/YoSheep/cauc_csa.git /var/www/cauc_csa
```

2. **设置 Apache2 默认主页**：

修改 Apache2 的配置文件，将项目设置为默认主页。

编辑 Apache2 的默认站点配置文件：

```bash
sudo nano /etc/apache2/sites-available/000-default.conf
```

找到 DocumentRoot，将其修改为项目的路径，例如：

```
DocumentRoot /var/www/cauc_csa
```

打开 Apache2 的主配置文件：

```bash
sudo nano /etc/apache2/apache2.conf
```

在文件末尾添加以下内容，确保项目路径的访问权限：

```
<Directory /var/www/cauc_csa>
    Options Indexes FollowSymLinks
    AllowOverride All
    Require all granted
</Directory>
```

3. **确保项目路径的权限**：

确保 Apache2 对项目目录有访问权限：

```bash
sudo chmod -R 755 /var/www/cauc_csa
```

4. **启用 Apache2 并重启服务**：

确保 Apache2 已启动并加载新的配置：

```bash
sudo systemctl restart apache2
```

5. **访问网站**：

在浏览器中输入服务器的 IP 地址或域名，即可访问网站。例如：

```
http://your-server-ip/
```

如果看到主页加载成功，恭喜你，部署完成！

### END

欢迎大家参与开发和改进！

有任何问题或建议，欢迎通过 Issue 或 PR 的方式提交！💻

