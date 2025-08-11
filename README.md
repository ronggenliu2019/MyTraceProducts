# Avatar Live Stream

一个使用MediaPipe和WebGL技术的实时头像动画应用，可以通过网络摄像头捕捉面部表情并将其映射到卡通头像上。

## 功能特点

- 实时面部表情捕捉
- 多种卡通头像选择（熊猫、机器人、猫咪）
- 头部运动和嘴部动作追踪
- 使用WebGL进行GPU加速渲染
- 自动降级到2D Canvas渲染
- 支持移动设备和桌面浏览器

## 系统要求

- 现代网络浏览器（Chrome、Firefox、Edge、Safari等）
- 网络摄像头
- 支持WebGL的图形硬件（可选，但推荐）
- Python 3.x（用于运行本地服务器）

## 安装和运行

### 使用HTTPS服务器（推荐）

由于浏览器安全限制，访问摄像头需要HTTPS连接或localhost。我们提供了一个简单的HTTPS服务器：

1. 确保已安装Python 3.x
2. 在项目目录中运行HTTPS服务器：

```bash
python https_server.py
```

3. 在浏览器中访问：https://localhost:8443/avatar-live-stream.html
4. 接受自签名证书安全警告
5. 允许浏览器访问您的摄像头

### 使用HTTP服务器（仅限本地开发）

如果您只在localhost上开发，也可以使用HTTP服务器：

```bash
python secure_server.py
```

然后访问：http://localhost:8080/avatar-live-stream.html

## 故障排除

### 常见问题

1. **摄像头无法访问**
   - 确保使用HTTPS或localhost
   - 检查浏览器是否有摄像头权限
   - 尝试重新加载页面并再次授予权限

2. **WebGL渲染问题**
   - 检查浏览器是否支持WebGL
   - 更新图形驱动程序
   - 应用会自动降级到2D Canvas渲染

3. **MediaPipe加载失败**
   - 检查网络连接
   - 清除浏览器缓存
   - 应用会自动尝试从备用CDN加载

## 技术细节

- **前端**：HTML5, CSS3, JavaScript
- **图形渲染**：WebGL2/WebGL1 with fallback to 2D Canvas
- **面部识别**：MediaPipe Face Mesh
- **服务器**：Python HTTP/HTTPS Server

## 许可证

MIT