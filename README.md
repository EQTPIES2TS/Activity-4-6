# Activity-4-6
## Activity 4 - Intent Passing
### Codes:
- XML:
  - Main:
  
     <TextView
        android:text="Enter your name: "
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true"
        android:layout_alignParentLeft="true"
        android:layout_alignParentStart="true"
        android:layout_marginLeft="32dp"
        android:layout_marginTop="32dp"
        android:layout_marginStart="22dp"
        android:id="@+id/textView"
        android:textSize="24sp"/>

    <Button
        android:text="continue"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/someUserText"
        android:layout_alignRight="@+id/textView"
        android:layout_alignEnd="@+id/textView"
        android:layout_marginRight="13dp"
        android:layout_marginEnd="13dp"
        android:layout_marginTop="56dp"
        android:id="@+id/go_btn" />

    <EditText
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:inputType="textPersonName"
        android:ems="10"
        android:layout_below="@+id/textView"
        android:layout_alignLeft="@+id/textView"
        android:layout_alignStart="@+id/textView"
        android:layout_marginLeft="20dp"
        android:layout_marginStart="20dp"
        android:layout_marginTop="29dp"
        android:id="@+id/someUserText" />
</LinearLayout>
  - Second:
  
  <?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical" android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:text="WELCOME BACK"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true"
        android:layout_alignParentLeft="true"
        android:layout_alignParentStart="true"
        android:layout_marginLeft="96dp"
        android:layout_marginStart="96dp"
        android:layout_marginTop="54dp"
        android:id="@+id/textView2"
        android:textSize="24sp"/>

    <TextView
        android:text="TextView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@+id/textView2"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="84dp"
        android:id="@+id/result_txt"
        android:textSize="18sp"/>
</LinearLayout>
- Java:
  - Main:
  package com.example.patrick.intentpassing;

import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

    final EditText et= (EditText) findViewById(R.id.someUserText);
        Button b = (Button) findViewById(R.id.go_btn);

        b.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick(View view){
                Intent intent = new Intent(MainActivity.this, Second.class);
                intent.putExtra("userName", et.getText().toString());
                startActivity(intent);
            }
        });
    }


}

  - Second:
  package com.example.patrick.intentpassing;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.widget.TextView;

public class Second extends AppCompatActivity{

    @Override
    protected void onCreate(Bundle savedInstanceState){
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);

        TextView nameView = (TextView) findViewById(R.id.result_txt);
        nameView.setText(getIntent().getExtras().getString("userName"));
    }

}
### Screenshots:
![3](https://cloud.githubusercontent.com/assets/16644615/20474000/27f6caac-afff-11e6-876f-69e59e66cadf.PNG)
![4](https://cloud.githubusercontent.com/assets/16644615/20474001/2801a15c-afff-11e6-8934-6871c8b644a4.PNG)
