## spring遇到问题总结

1. 网页单机样式有效,运行样式无效

   因为porm.xml中未导入jquery和bootstrap,解决方案

   ```xml
   <dependency>
   	<groupId>org.webjars</groupId>
   	<artifactId>bootstrap</artifactId>
   	<version>3.3.7</version>
   </dependency>
   <dependency>
   	<groupId>org.webjars</groupId>
   	<artifactId>jquery</artifactId>
     <version>3.4.1</version>
   </dependency>
   ```

2. bootstarp样式失效

   需要在index导入bootstrap前导入jQuery包

   ```html
   <script src="js/jquary.min.js"></script>
   <script src="js/bootstrap.min.js" type="application/javascript"></script>
   ```

3. 修改端口号

   在application.properties中加入

   ```xml
   server.port=8887
   ```

4. 

### 使用github账户登录技术总结

1. 在github中创建OAuth Apps

   创建过程中homepage url为项目网址,authorization callback url为项目跳转时路径,错误无法成功跳转

2. 在html登录中加入

   1. 具体加入参数**client_id**,redirect_uri,scope,state
   2. 其中第一个参数用?连接,其他用&连接,client_id为必须元素
   3. 具体各参数含义详见[aouth文档](https://developer.github.com/apps/building-oauth-apps/authorizing-oauth-apps/)

   ```html
    <li><a href="https://github.com/login/oauth/authorize?client_id=79567d245a0687dcf739&redirect_uri=http://localhost:8887/callback&scope=user&state=1">登录</a></li>
   ```

3. 内部详细流程如下

   ![github登录](/Users/l/Desktop/code/communtiy/github登录.png)







