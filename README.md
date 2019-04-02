- stringify
- scope == variable angular5
- root scope == service angular5
# Shared component, SharedModule tanya zaki
# Sample Code
D:\PROJECT\RESEARCH\angular 5\ng5

## Menggunakan ngModel
- Buka app.module.ts, tambahkan
```
import { FormsModule } from '@angular/forms';
...
imports: [
  ...
  FormsModule,
  ...
]
...  
```

## Create new Project
```
ng new ng5 --style=scss --routing
```
## Routing 
- Pastikan saat create new project gunakan option '--routing'
- app-routing.module.ts tambahkan
```
import {HomeComponent} from './home/home.component';
import {AboutComponent} from './about/about.component';
...
const routes: Routes = [
  {
    path:'',
    component:HomeComponent
  },
  {
    path:'about/:id',
    component:AboutComponent
  }
];
```
- penggunaan ->
```
<li><a routerLink="about/48">About</a></li>
```
-nangkap :id (48)
```
import { ActivatedRoute } from '@angular/router';
```
```
constructor -> private route : ActivatedRoute
atau
tidak ditaruh constructor -> route : ActivatedRoute = new ActivatedRoute()
```
```
this.route.params.subscribe(res => console.log(res.id));
```
- pindah halaman
```
import { Router } from '@angular/router';
```
```
constructor -> private router : Router
atau
tidak ditaruh constructor -> router : Router = new Router()
```
```
this.router.navigate(['path']); //'path' lihat di app-routing.module.ts
```
- membawa parameter
```
this.router.navigate([''], { queryParams: { naruto: 1 } }); //https://angular.io/api/router/NavigationExtras
```
- nangkap param 
```
constructor -> private activatedRoute: ActivatedRoute
this.activatedRoute.queryParams.subscribe(res => console.log(res.naruto))

```

## Run Project
```
ng serve --environment=prod --port=4100

``` 

## Create Service
untuk sharing data antar komponen contoh http request (post get)
```
ng generate service data
```

## Generate new component
```
ng generate component home --or-- ng g c home

```

## Environment
pada folder 'environments' ada 2 file, environment.prod.ts dan environment.prod.ts, untuk jalankan environtment production
```
ng serve --environment=prod --port=4100     	//running
ng build --prod --environment=prod		//deploying

```
ref : https://www.oodlestechnologies.com/blogs/Setting-Up-Environment-Variables-In-Angular-5

## library
```
npm install moment --save    //akan kesimpan di node_modules
```
- Penggunaan
```
import * as moment from 'moment';
....
moment().format('MMMM Do YYYY, h:mm:ss a')
```

## Directive
```
ng generate directive highlight
```
directive sederhana
```
import { Directive, ElementRef } from '@angular/core';

@Directive({
  selector: '[appHighlight]'
})
export class HighlightDirective {

  constructor(el: ElementRef) {
    el.nativeElement.style.backgroundColor = 'yellow';
  }

}
```
appHighlight boleh dipakai komponen apa saja 
```
<p appHighlight>Highlight me!</p>
```
