# Activity-4-6
## Activity 4 - Intent Passing
### Codes:
- XML:
  - Main:
  
     ![1a](https://cloud.githubusercontent.com/assets/16644615/20474140/128c150e-b000-11e6-987f-81961fb3eea0.PNG)
![1b](https://cloud.githubusercontent.com/assets/16644615/20474141/12b82e28-b000-11e6-8964-6ecb78d8eb4e.PNG)

  - Second:
  
  
![1c](https://cloud.githubusercontent.com/assets/16644615/20474142/12db8864-b000-11e6-8bac-d0f76b20bb36.PNG)
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

## Activity 5 Intent Multiple

### Codes:
- XML
  - Main:
  - Second:
- Java
  - Main:
  - Second:

### Screenshots:

