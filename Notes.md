# GET STARTED!
**Create a new angular project on the current location**


`ng new my-first-app`


**Start the serve**


`ng serve`

For some users, you might need to add `sudo` in front of the command 



**Components**

Components are basically typescript class

Each component should have its own folder with the component name

<img width="246" alt="截屏2023-07-21 12 00 20" src="https://github.com/Ekko272/AngularLearning/assets/122116946/bccdb32b-c2f1-4f93-a076-3bb383b7403f">

**Create a server.component.html file under the server folder**

In your server.component.ts:

```typescript
import { Component } from "@angular/core";

@Component({
    selector: 'app-server',
    templateUrl: './server.component.html'
})
export class ServerComponent{
}
```

Now in app.module.ts, we need to add this component:

```typescript
import { ServerComponent } from './server/server.component';

@NgModule({
  declarations: [
    AppComponent,
    ServerComponent
  ],
  imports: [
    BrowserModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Each component.ts must have a `templateUrl:` to an HTML file or have a `template:` to create an inline HTML

```
template: `
    <app-server></app-server>
  `
```
**Notice: Remember to save every file after editing, or it would cause a compiler error**

Now we can use `<app-server><app-server>` in our app.compnent.html file. 

It will display the content of server.component.html

A shortcut for creating a new component is using the command line. (make sure you are using a new command window to maintain the compiler running)

`ng g c yourcomponentname`

servers.component.ts:

```typescript
@Component({
  selector: 'app-servers',
  //Change the selector as attributes:
  //selector: ['app-servers']
  //now we can use this way in HTML: <div app-servers><div>
  //selector: '.app-servers'
  //<div class="app-servers"><div>


  templateUrl: './servers.component.html',
  /* Also can use inline HTML code
  template: `
    <app-server></app-server>
  `
  */
  styleUrls: ['./servers.component.css']
})
export class ServersComponent {

}
```

**Databinding**

<img width="1515" alt="截屏2023-07-25 12 04 32" src="https://github.com/Ekko272/AngularLearning/assets/122116946/337d66df-b4f4-4aa4-b851-28b5d9a71ae9">

{{}} The content inside this has to be a string. It can be an element or a function as long as it returns a string.

```typescript
//in HTML template
<p>{{'Server'}} with ID {{serverId}} is {{serverName}}</p>


//in ts
import { Component } from "@angular/core";
@Component({
    selector: 'app-server',
    templateUrl: './server.component.html'
})
export class ServerComponent{
    serverId: number=10;
    serverName: string='offline';
}
```

**Propertybinding**

[] binding a property












