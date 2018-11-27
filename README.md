# Lesson 1  Setup ionic
**1. Install the Inoic CLI**<br>
Install: <code>npm install -g ionic</code> <br>
Check Version: <code>ionic --version</code> <br> 
<br>
**2. Generating First Project**<br>
<code>ionic start MyFirstApp blank --type=angular</code><br>
Creat a new application with all of the boilerplate code and files you need <code>ionic start</code><br>
Templates aside from <code>blank</code> and it is very useful if they closedly match the structure of the application what you want to build<br>
<br>
**3. Change directory to your new ionic project**<br>
<code>cd MyFirstApp</code><br><br>
**4. Running the application**<br>
<code>ionic serve</code><br>
This will open up a new browser with your application open in it and running on a local web server.<br><br>

# Lession 2  Various files and folders contained within your project
### src
This folder contains most of the files and folders that you will actually be working on to create your application<br>
### app
Most of the code for your application will live inside of this app folder:<br>
<ul> <strong>app.module.ts</strong><br>
  Module files use an Angular concept call <code> @NgModule</code>. The basic idea is that modules allow an application to be split up into "chunks" of related functionality.大部分时间不用动这些文件。</ul>
<ul><strong>app-routing.module.ts</strong><br>
  Creates a module called<code>AppRoutingModule</code>which is then imported into the root module.目的是定义应用中使用的routes. 简单来说，我们想定义URL matches up to which component/page.如果用户去<code>/home</code>路径，我们经常显示 home page/component. 这并不需要放在它自己的module，you could just set these routes up directly in the main root module<br></ul>
<ul><strong>app.component.html</strong></code><br>
  这个文件夹里包含一个根元件的样板：<br>
  
```
<ion-app>
    <ion-router-outlet></ion-router-outlet>
</ion-app>
```
<code>\<ion-router-outlet\></code>控制哪些组件被显示给用户（基于现在的路径）。如果用户在<code>/Home</code>路径，那么，home page 会显示。<br></ul>
<ul><strong>pages</strong><br>
 The pages folder contain all the pages for our application: home page, login page, product detail page...<br>
  A page/component is made up primarily of:<br>
  <ul>*.module.ts导入需要的方程<br>
      *.page.ts 定义逻辑/行为关系与相关的页面<br>
      *.page.html 定义样本/view <br>
    *.page.scss 定义式样<br></ul></ul>

<ul><strong>www</strong><br>
  The <strong>www</strong> folder contains output of the build process for application, 并且这里的代码是用户使用这个应用时真正运行的代码，尽量不要动这个文件。如果分布这个应用带网上，这个code folder就是上传到server hosting the application.</ul><br>
<ul><strong>package.json</strong><br>
  configuration information for your project. it lists all the dependencies(external libraries/packages required to make your project work) for your application.<br></ul>
 
 ```
  import {Component } from '@angular/core';
  ```
  <ul>从 <code>@angular/core</code> 导出 package.<br></ul>

# Lesson 3 : Ionic CLI Commands
### Serving your Application
View the Ionic application which you working on in the browswer by running:

```
ionic serve
```

**Ionic Lab** which will display your project in the ionic lab interface. This will give you side-by-side comparison of iOS and Android:<br>
Install the package:

```
npm install --save @ionic/lab
```
then, you can add <code>-l</code>flag to the <code>serve</code> command:

```
ionic serve -l
```

### Generate
To create more components, you can just <code>ionic generate</code> command to do it automatically with some handy boilerplate code in place.<br>
* page
* component
* directive
* service
To use the command you just run or you can manually supply teh name of your page/component/directive/service to the command like:

```
ionic g page
ionic g page/MyPage
ionic g service services/MyService
```

