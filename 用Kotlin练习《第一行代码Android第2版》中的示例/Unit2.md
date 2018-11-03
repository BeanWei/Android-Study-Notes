### 2.2.2  创建加载布局
```
:first_layout.xml
  <Button
            android:id="@+id/button_1"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Button 1"/>
            
:AanroidMainfest.xml ע��
  <activity android:name=".FirstActivity">
      <intent-filter>
          <action android:name="android.intent.action.MAIN" />
              <category android:name="android.intent.category.LAUNCHER" />
      </intent-filter>
  </activity>
```


### 2.2.4 在活动中使用toast
```
:FirstActivity.kt
  setContentView(R.layout.first_layout)
        button_1.setOnClickListener {
            Toast.makeText(
                this,
                "you had press the Button 1 ~",
                Toast.LENGTH_SHORT
            ).show()
        }
```      
        
### 2.2.5 在活动中使用menu
```
:main.xml
<item
    android:id="@+id/add_item"
    android:title="Add" />
<item
    android:id="@+id/remove_item"
    android:title="Remove" />

:FirstActivity.kt
··· ···
override fun onCreateOptionsMenu(menu: Menu?): Boolean {
        menuInflater.inflate(R.menu.main, menu)
        return true
 }

override fun onOptionsItemSelected(item: MenuItem?): Boolean {
      when (item?.itemId) {
          R.id.add_item -> Toast.makeText(this, "you click add", Toast.LENGTH_SHORT).show()
          R.id.remove_item -> Toast.makeText(this, "you click remove", Toast.LENGTH_SHORT).show()
      }
      return true
  }
```  

  
### 2.2.6 销毁一个活动
```
:FirstActivity.kt
···
button_1.setOnClickListener {
    finish()
}
···
```


### 2.3.1 显式Intent
```
val intent = Intent()
intent.setClass(this, SecondActivity :: class.java)
startActivity(intent)
```


### 2.3.2 隐式Intent
```
val intent = Intent()
intent.setAction("ACTION_START")
startActivity(intent)
```