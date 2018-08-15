# 我的程序没bug
## 记录一些npm使用时候的报错

* **npm总是报错：unable to verify the first certificate**
  因为npm install走的是https协议，需要通过数字证书来保证的
* **解决方案**
  1. 取消ssl验证：npm config set strict-ssl false
  2. 如果还没成功，则将npm源更换为国内镜像：
      npm config set registry http://registry.cnpmjs.org/
      npm config set registry http://registry.npm.taobao.org/
  3. 升级：npm install npm -g --ca=null 或者 npm config set ca=""