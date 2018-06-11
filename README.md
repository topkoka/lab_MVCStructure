# 1.mvc structure
## 1.1.binding

* 1.1 เรียกใช้  binding

#### app/gradle
```
 dataBinding{enabled true}
```

## 1.2.mvc

* 2.1 สร้าง package รูปแบบ MVC

#### /java/package

#### activity
#### manager
#### util
#### view 
#### fragment


* 1.2.2 สร้าง MainApplication.java 

#### java/app

-create 
MainApplication.java

* 1.2.3 add MainApplication
#### androidmanifest.xml

```
 android:name=".MainApplication"
```

## 1.3.liberry

* 1.3.1 เรียกใช้ liberry
#### settings.gradle
```
 ,':TheCheeseLibrary'  
 
```
   * 1.3.1.1  add library เข้า ไปใน app
   #### app/gradle
   
   ```
   
   implementation project(':TheCheeseLibrary')
   
   ```

* 1.3.2 ใช้ Contextor ที่  MainApplication

#### MainApplication.java 
```

  Contextor.getInstance().init(getApplicationContext()); 
 
```

## 1.4.copy template

* 1.4.1 ก๊อปปี้ template จาก libarry

#### manager

- singletontemplate.java

#### fragment

- fragmenttemplate

#### view

- customviewtemplate

- customviewgrouptemplate

## 1.5.create fragment_main


* 1.5.1 สร้าง fragment เพื่อใช้ แทน activity_main

#### res/layout

create
 - fragment_main.xml 


* 5.2 ก๊อปปี้ template fragmentTemplat เปลี่ยนชื่อเป็น MainFragment

#### fragment

create
 - MainFragment.java


## 1.6.add mainfragment to mainactivity 

* 1.6.1 add fragment เข้าไปที่ activity

#### activity_main.xml

``` 
 	  <FrameLayout
            android:id="@+id/contentContainer"
            android:layout_width="match_parent"
            android:layout_height="match_parent"/>

```

#### MainActivity.class

```  
  if (savedInstanceState == null){
            getSupportFragmentManager().beginTransaction()
                    .add(R.id.contentContainer, MainFragment.newInstance())
                    .commit();
        }
	 
``` 
