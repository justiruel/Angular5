app.module.ts -> import { FormsModule } from '@angular/forms';  // untuk gunakan ngModel

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
