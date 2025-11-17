# DEVELOPING-AN-ANDROID-APPLICATION-TO-PERFORM-MATHEMATICAL-OPERATION.-

## AIM:
To develop an android application to perform mathematical operation.

## APPARATUS REQUIRED:
ØComputer
ØAndroid studio software


## THEORY:
The platform uses signed two's complement integer arithmetic with int and long primitive types. The developer should choose the primitive type to ensure that arithmetic operations consistently produce correct results, which in some cases means the operations will not overflow the range of values of the computation. The best practice is to choose the primitive type and algorithm to avoid overflow. In cases where the size is int or long and overflow errors need to be detected, the methods add, subtract multiply, and throw an Arithmetic exception when the results overflow. For other arithmetic operations such as divide, absolute value, increment by one, decrement by one, and negation, overflow occurs only with a specific minimum or maximum value and should be checked against the minimum or maximum as appropriate.



## PROCEDURE:
1. Open Android Studio and then click on File -> New -> New project. 2. Then type the application name as “ex.no.1″ and click Next.
3. Then select the Minimum SDK as shown below and click next. 4. Then select the Empty Activity and click next.
5. Finally click Finish.
6. Click on app -> java -> com.example -> MainActivity.java
7. Now click on Text and type the program, so now the programming part of the main activity is completed.
8. Click on app -> res -> layout -> activity_main.xml.
9. Now click on Text and type the program, so now the designing part of Activity main is also completed.
10. Select the suitable available device to display the output. 11. Now run the application to see the output. 


## PROGRAM:
package com.example.myapplication3;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity implements View.OnClickListener {

    Button buttonAdd, buttonSub, buttonMul, buttonDiv;
    EditText editTextN1, editTextN2;
    TextView textView;
    int num1, num2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        buttonAdd = findViewById(R.id.btn_add);
        buttonSub = findViewById(R.id.btn_sub);
        buttonMul = findViewById(R.id.btn_mul);
        buttonDiv = findViewById(R.id.btn_div);
        editTextN1 = findViewById(R.id.number1);
        editTextN2 = findViewById(R.id.number2);
        textView = findViewById(R.id.answer);

        buttonAdd.setOnClickListener(this);
        buttonSub.setOnClickListener(this);
        buttonMul.setOnClickListener(this);
        buttonDiv.setOnClickListener(this);

    }

    public int getIntFromEditText(EditText editText) {
        if (editText.getText().toString().equals("")) {
            Toast.makeText(this, "Enter number", Toast.LENGTH_SHORT).show();
            return 0;
        } else
            return Integer.parseInt(editText.getText().toString());
    }

    @Override
    public void onClick(View view) {
        num1 = getIntFromEditText(editTextN1);
        num2 = getIntFromEditText(editTextN2);

        int id = view.getId(); // Get the ID once

        if (id == R.id.btn_add) {
            textView.setText("Answer = " + (num1 + num2));
        } else if (id == R.id.btn_sub) {
            textView.setText("Answer = " + (num1 - num2));
        } else if (id == R.id.btn_mul) {
            textView.setText("Answer = " + (num1 * num2));
        } else if (id == R.id.btn_div) {
            // Ensure num2 is not zero to avoid division by zero error
            if
            (num2 == 0) {
                Toast.makeText(this, "Cannot divide by zero", Toast.LENGTH_SHORT).show();
                textView.setText("Answer = Error");
            } else {
                textView.setText("Answer = " + ((float) num1 / (float) num2));
            }
        }
    }
}
activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:orientation="vertical"
    android:padding="20dp"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Simple calculator!"
        android:layout_gravity="center"
        android:textStyle="bold"
        android:layout_margin="50dp"
         android:textSize="30sp"/>

    <EditText
        android:id="@+id/number1"
        android:hint="Enter number"
        android:layout_margin="30dp"
        android:inputType="number"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <EditText
        android:id="@+id/number2"
        android:hint="Enter number"
        android:layout_margin="30dp"
        android:inputType="number"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <LinearLayout
        android:layout_marginTop="30dp"
        android:orientation="horizontal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <Button
            android:id="@+id/btn_add"
            android:text="+"
            android:textSize="30sp"
            android:layout_marginEnd="5dp"

            android:layout_width="wrap_content"
            android:layout_height="wrap_content"/>

        <Button
            android:id="@+id/btn_sub"
            android:text="-"
            android:textSize="30sp"
            android:layout_marginEnd="5dp"

            android:layout_width="wrap_content"
            android:layout_height="wrap_content"/>

        <Button
            android:id="@+id/btn_mul"
            android:text="*"
            android:textSize="30sp"
            android:layout_marginEnd="5dp"

            android:layout_width="wrap_content"
            android:layout_height="wrap_content"/>

        <Button
            android:id="@+id/btn_div"
            android:text="/"
            android:textSize="30dp"
            android:layout_marginEnd="5dp"

            android:layout_width="wrap_content"
            android:layout_height="wrap_content"/>

    </LinearLayout>

    <TextView
        android:id="@+id/answer"
        android:layout_gravity="center"
        android:layout_marginTop="30dp"
        android:textSize="30sp"
        android:textStyle="bold"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

</LinearLayout>



## OUTPUT:
<img width="1040" height="557" alt="image" src="https://github.com/user-attachments/assets/d1695077-4107-44f2-a74d-bc874abb3d57" />




## RESULT:
Thus, the Android app for basic operations (addition, subtraction, multiplication, and division) is developed and the output is verified.

