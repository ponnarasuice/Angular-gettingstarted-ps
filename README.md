# Angular-gettingstarted-ps
# introduction
## what is Angular
JS framework used in the frontend application
## why Angularjs
modular design, buildin backend integration, powerful data binding, expressive html
## how they marketed to world
moderen js framework, will enhance the productivity who uses
## structure
each applicaiton = several components + services
![Alt text](https://github.com/ponnarasuice/Angular-gettingstarted-ps/blob/master/readme_images/anatomyofangular.PNG "anatomy")
component = html template + classes + metadata
![Alt text](https://github.com/ponnarasuice/Angular-gettingstarted-ps/blob/master/readme_images/component.PNG "component")
modules -> componenents are mapped to the application by modules. min 1 module mandate for the application
![Alt text](https://github.com/ponnarasuice/Angular-gettingstarted-ps/blob/master/readme_images/modules.PNG "modules")


# steps to follow any application
## 1.each page - each component- design with requirement wireframe
main welcome page
![Alt text](https://github.com/ponnarasuice/Angular-gettingstarted-ps/blob/master/readme_images/welcome.PNG "welcome page")
product list page
![Alt text](https://github.com/ponnarasuice/Angular-gettingstarted-ps/blob/master/readme_images/productlist.PNG "productlist page")
product details page
![Alt text](https://github.com/ponnarasuice/Angular-gettingstarted-ps/blob/master/readme_images/productdetail.PNG "productdetail page")
created each component for each page. if component can be reused by 2 component we created sub component. all components are tied together by app comp or module. these are passed to main index page.
![Alt text](https://github.com/ponnarasuice/Angular-gettingstarted-ps/blob/master/readme_images/thisapparchitecture.PNG "this sample app architecture")

## 2.with design ready - get boiler code to getting started
- we can create manully the folder structure. but we have boiler code already available
- use angular quick start boiler code (https://github.com/angular/quickstart)
- use angular CLI tooling to create components and package structure 
(https://github.com/angular/angular-cli)
- use intructor boiler code for this sample app as some extra stuffs are added for this project 
(https://github.com/DeborahK/Angular-GettingStarted)
**APM-Start:** The starter files set up for use in VSCode, WebStorm, or other editors. Use this to code along with the course. (Updated for Angular version 4.3 or higher)
**APM-Final:** The completed files. Use this to see the completed solution from the course. (Updated for Angular version 4.3 or higher)

Download the github app folders and copy paste the APM-start files to APM.

## 3. any application - follow the following
- create the app folders > can get from boiler code
- add package definition package json / config files
- install the packages > npm install will install dependencies
- create app angular module > atleast one required for a project
- create main.ts > to add the angular module
- create main page > usually index.html


# selecting the language/ editors/ npm 
- **VSCode** is used here
- ECMA script based language is many. java script has versions ES2016, ES2015, ES 5 & lower or typescript language(superset of js or like js)
we use type script since it supports all the latest ecma standards. we cant use directly in browser as most of them yet to support es2015+.
so typescript are transpiled and use in application. usually we minifest the js and run in app.
- download npm and code in the machine. package manager and the other is serverjs frame work. browser js has limitation like threading, file reading etc. but server has no restrictions.

## First look on project folder
- Application usually have src -> which contains source files. here app sub-dir contains applicaiton specific files. will add more when requirements increase.
- 1st step with boiler code would be -> install dependencies using npm.
  >npm install // dwns dependencies mentioned in pacakge.json and put it in /node_modules. no need to check in these files. add them entries in .gitignore 

# concept 1 - modules
modules - for code organisation and variable out of global space in js. 
- ECMA2015 has specification for modules. as per ecma2015, modules are files with export or import which becomes modules
- angular also has ecma2015 module concept. Also it has its own angular modules.
- typescript also has modules

ECMA2015 modules - organize the code.
![Alt text](https://github.com/ponnarasuice/Angular-gettingstarted-ps/blob/master/readme_images/module_2015.PNG "ECMA 2015 Modules")
Angular modules - organize the application.
![Alt text](https://github.com/ponnarasuice/Angular-gettingstarted-ps/blob/master/readme_images/module_Angular.PNG "Angular Modules")

# concepts 2 - components
we write many components and make them work together. we return results to angular module.
**components** = template + class +metadata
- **template** : view layout with binding and directive
- **class** : code to support the view. property + methods
- **metadata** : defined with decorator. extra info **for the angular module**
![Alt text](https://github.com/ponnarasuice/Angular-gettingstarted-ps/blob/master/readme_images/component-eg.PNG "Angular Modules")
This has class component + metadata component
**meta data** - is A function that adds metadata to a class. prefixed with @. there are lot of decorators available in built.
selector value is used in the template associated with the class.
**import statement** - import from third party lib or own modules which exports. 
eg of angular own modules : @angular/core , @angular/animate, @angular/http, @angular/router

# concept 3 - bootstraping our application
we wrote component and templates. how to bring to the front end or to the angular app.
2 steps in bootstraping:
- index.html (single page application)
div
pm-root>pm-root>/div>   // **when angular see directive .passes from bootstrap module.  it checks the app module**

- App module: atleast one app **module** requires to a application. 

//usually ng module, browser module and our bootstrap module is present.
```
code:
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core'; 
import { AppComponent } from './app.component';

@NgModule({ // it decorator and has  array of elements
  declarations: [  AppComponent  ], // declares all the modules used in front page
  imports: [    BrowserModule  ], // external modules or own available to all the components
  providers: [],
  bootstrap: [AppComponent] // which is the first module to compile. this component contains the root selector in index.html
})
export class AppModule { }
```




