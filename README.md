# Zero-Devtools
Zero-Devtools

# 1. 概述
## 1.1. 简介
DevTools是开发者工具集，主要用于简化开发过程中的热部署问题。 热部署是指在开发过程中，当代码发生变化时，无需手动重启应用，
系统能够自动检测并重新加载修改后的代码，大大提高了开发效率
## 1.2. 原理
- 为什么同样是重启应用，为什么不手动重启，而是建议使用spring-boot-devtools进行热部署重启？

spring-boot-devtools使用了两个类加载器ClassLoader，一个ClassLoader加载不会发生更改的类（第三方jar包），
另一个ClassLoader（restart ClassLoader）加载会更改的类（自定义的类）。 后台启动一个文件监听线程（File Watcher），
监测的目录中的文件发生变动时， 原来的restart ClassLoader被丢弃，将会重新加载新的restart ClassLoader。
因为文件变动后，第三方jar包不再重新加载，只加载自定义的类，加载的类比较少，所以重启比较快

# 2. 功能

# 3. 使用
## 3.1. 测试
1. 启动Spring Boot应用 
2. 访问 [http://localhost:8080/](http://localhost:8080/)，查看结果
3. 修改接口返回值，再次访问接口，此时不用重启应用就可以看到最新的值了

# 4. 其他

# 5. 参考