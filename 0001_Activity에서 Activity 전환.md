# [액티비티에서 다른 액티비티로 전환하는 방법]

- Intent를 사용하기!
저는 MainActivity에서 SecondActivity로 전환하는 방법을 택했습니다.
(사용자가 설정한 다른 액티비티에서 다른 액티비티로 전환하는 방법도 동일합니다.)


- MainActivity.java
-패키지명은 ssoryeonsdiary입니다.
-전 메인엑티비티에 이미지버튼을 세 개 배치하였는데, 왼쪽부터 홈, 두번째 엑티비티, 세번째 엑티비티로 전환하는 이미지버튼입니다.
-메인엑티비티에서는 두번째, 세번째 이미지버튼 기능만 구현하면 되므로 Intent를 이용해서 구현해주었습니다.

```java
 ImageButton eat1btn = findViewById(R.id.eat1btn);
        eat1btn.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick(View view){
                Intent intent = new Intent(MainActivity.this, SecondActivity.class);
                startActivity(intent);
            }
```

이미지버튼, 버튼, 이미지 모두 상관없습니다.
해당 위젯에 setOnClickListener를 연결하고 
Intent intent = new Intent(현재액티비티, 전환하려는액티비티) 이렇게 연결해주고
startActivity(intent) 이렇게 연결해주시면 됩니다.
해당 코드와 거의 복붙 수준으로 구현하시면 액티비티 전환은 잘 되실 것 같습니다.

```java
package com.example.ssoryeonsdiary;

import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.ImageButton;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        ImageButton eat1btn = findViewById(R.id.eat1btn);
        eat1btn.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick(View view){
                Intent intent = new Intent(MainActivity.this, SecondActivity.class);
                startActivity(intent);
            }


        });



        ImageButton eat2btn = findViewById(R.id.eat2btn);
        eat2btn.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick(View view){
                Intent intent = new Intent(MainActivity.this, ThirdActivity.class);
                startActivity(intent);
            }


        });

    }
```
