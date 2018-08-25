# ngFor
透過`*ngFor="let user of users`寫迴圈，
其中`users`是一個在.ts fule中宣告過的array，
`user`去拿`users`裡面的值。
```
<li *ngFor="let user of users">
    <h2> {{ user.name }} </h2>
    <h2> {{ user.age }} </h2>
</li>
```

***

# ngIf
下方兩種寫法可以表達一樣的意思。
在`users`後加`?`是為了防止`users`沒有存在但又去拿他的`length`而導致的error。
```
<ul *ngIf="users?.length > 0" >
    <li *ngFor="let user of users">
        <h2> {{ user.name }} </h2>
        <h2> {{ user.age }} </h2>
    </li>
</ul>

<ul *ngIf="users?.length == 0" >
    <h2> There's no user </h2>
</ul>
```

```
<ul *ngIf="users?.length > 0; else noUser" >
    <li *ngFor="let user of users">
        <h2> {{ user.name }} </h2>
        <h2> {{ user.age }} </h2>
    </li>
</ul>

<ng-template #noUser>
    <h2> There's no user </h2>
</ng-template>
```
