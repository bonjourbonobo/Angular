# Basic Step
1. create app-routing module
2. import RouterModule
3. create routes
4. router outlet
5. add links

# Create app-routing Module
`ng g m app-routing --flat --module=app.module`

# Import RouterModule
在app-routing.module中移除 `CommonModule` in app-routing module, 
並 import `RouterModule`, `Routes`
```
import { NgModule } from '@angular/core';
import { RouterModule, Routes } from '@angular/router';

const routes: Routes = [];

@NgModule({

  exports:[
    RouterModule
  ],
  imports: [
    RouterModule.forRoot(routes)
  ],
  declarations: []
})
export class AppRoutingModule { }
```

# Router Outlet
在app-component.html檔案中加入`<router-outlet></router-outlet>`

# Create Routes
在app-routing.module.ts中加入要有URL分頁的component。
```
import { UserComponent} from '../app/components/user/user.component';
import { HomeComponent} from '../app/components/home/home.component';
import { PostComponent} from '../app/components/post/post.component';

const routes: Routes = [
  {path: '', component: HomeComponent},
  {path: 'user', component: UserComponent},
  {path: 'post', component: PostComponent}
];
```

# 設定btn會連到的URL
使用`routerLink`
```
<button class="btn btn-secondary" routerLink="/user">User Section</button>
<button class="btn btn-secondary" routerLink="/post">Post Section</button>
```


