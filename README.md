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
### 1. Serving your Application
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

### 2. Generate
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

### 3. Installing Packages or Plugins

```
npm install some-package --save
ionic cordova plugin add some-plugin
cordova plugin add some-plugin
```
If you want to use Ionic Native to access the plugin, you should install the Ionic Native as well. **DO NOT** DO THIS IF YOU USING CAPACITOR.

```
npm install @ionic-native/some-plugin@beta --save
```
**NOTE** During the beta period, it is important that you install Ionic Native plugins using the <code>@beta</code> version. When importing plugins from Ionic Native into your project you should also import from <code>/ngx</code> e.g:

```
import { Facebook } from '@ionic-native/facebook/ngx';
```

### 4. Creating a Build
Most time we use <code>serve</code> to run our application, 有时会需要 create a build 在www 文件内，可以之间进入。当你要run your code on the web. To create a build:

```
ionic build
```
or to create an optimised production build you can run:

```
ionic build --prod
```
### 5. Using Capacitor

Ionic  CLI has integrations for Capacitor. To initialise Capacitor in your project you can just add a platform:

```
ionic cap add android
//or
ionic cap add ios
```
To sync your project with Capacitor. This will copy over your built application from the <code>www</code> folder:

```
ionic cap sync
// or
ionic cap update
```

# Lession 4 : Decorators
# Lession 5 : Classes
### 1. What is a class?

```
class Person {
  constructor(name, age){
    this.name = name;
    this.age = age;
  }
  setAge(age){
    this.age = age;
    return true;
  }
  getAge(){
   return this.age;
  }
  setName(name){
    this.name = name;
    return true;
  }
  getName(){
    return this.name
  }
  isOld(){
    return this.age > 70;
  }
}
```
<code>constructor</code> is run whenever we create an instance of this class. Once we have our class defined which acts as blueprint for creating objects, we could create a new **Person** objects like this:

```
let john = new Person('John', 32);
let louise = new Person('Louise', 28);
let david = new Person('David', 72);
console.log(john.isOld());
console.log(louise.isOld());
console.log(david.isOld());
```

What a class looks like in Inonic:

```
import { Component } from '@angular/core';
import { ModalController } from '@ionic/angular';
import { SomePage } from '../some-page/some-page.page';
 @Component({
    selector: 'app-page-home',
    templateUrl: 'home.page.html',
    styleUrls: ['home.page.scss']
  })
  export class HomePage {
    constructor(private modalCtrl: ModalController){
  }
}
```
Importing <code>Component</code> from <code>@angular/core</code> which allows us use the <code>@Component</code> decorator, and **ModalController** from the Ionic library which we can use to create modal overlays(pop up a page on top of our current page)<br>
<br>
Also, importing **SomePage** which is a class/component of our own createion.The path for this simply follows the directory structure of your project, we have the **SomePage** component defined inside a folder called pages which is one level above the current file. <br>
