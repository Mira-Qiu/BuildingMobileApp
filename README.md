## Lesson 1  Setup ionic
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

## Lession 2  Various files and folders contained within your project
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
<code><ion-router-outlet></code>控制那些组件被显示给用户（基于现在的路径）。如果用户在<code>/Home</code>路径，那么，home page 会显示。<br></ul>
 
 
