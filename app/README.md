# Ex.No:7 Develop a simple calculator using android studio.
## AIM:
To develop a program to develop a simple calculator in Android Studio.

## EQUIPMENTS REQUIRED:
Android Studio(Min.required Artic Fox)

## ALGORITHM:
### Step 1: 
Open Android Stdio and then click on File -> New -> New project.

### Step 2: 
Then type the Application name as calculator and click Next.

### Step 3: 
Then select the Minimum SDK as shown below and click Next.

### Step 4: 
Then select the Empty Activity and click Next. Finally click Finish.

### Step 5: 
Design layout using UI components in activity_main.xml.

### Step 6: 
Display the calculator operation in MainActivity file.

### Step 7: 
Save and run the application.

## PROGRAM:
```java
 Program to print the text “calculator operation”.
Developed by: ASHWIN A O
Registeration Number : 212220230005
```
### activity_main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/calc"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="293dp"
        android:layout_height="213dp"
        android:outlineAmbientShadowColor="@color/black"
        android:text="Simple\nCalculator"
        android:textAlignment="center"
        android:textColor="@color/black"
        android:textSize="50dp"

        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.092"
        tools:ignore="InvalidId,MissingConstraints" />

    <EditText
        android:id="@+id/editTextNumber1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="number"
        android:text="Number 1"
        android:textAlignment="gravity"
        android:textColor="@color/black"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.314" />

    <EditText
        android:id="@+id/editTextNumber2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:ems="10"
        android:inputType="number"
        android:text="Number 2"
        android:textColor="@color/black"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editTextNumber1"
        app:layout_constraintVertical_bias="0.097" />

    <TextView
        android:id="@+id/textView1"
        android:layout_width="385dp"
        android:layout_height="106dp"
        android:text="Result"
        android:textAlignment="center"
        android:textColor="@color/black"
        android:textSize="35dp"

        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.539"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.993"
        tools:ignore="InvalidId,MissingConstraints" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:backgroundTint="@color/black"
        android:text="+"
        android:textAppearance="@style/TextAppearance.AppCompat.Large"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.566" />

    <Button
        android:id="@+id/button2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:backgroundTint="#808080"
        android:text="--"
        android:textAppearance="@style/TextAppearance.AppCompat.Large"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.64" />

    <Button
        android:id="@+id/button3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:backgroundTint="@color/black"
        android:text="x"
        android:textAppearance="@style/TextAppearance.AppCompat.Large"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.715" />

    <Button
        android:id="@+id/button4"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:backgroundTint="#808080"
        android:text="%"
        android:textAppearance="@style/TextAppearance.AppCompat.Large"
        android:textColor="@color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.79" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
### MainActivity.java
```java
package com.example.sinmplecalc;



import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Button btnsum = (Button) findViewById(R.id.button);
        Button btnsub = (Button) findViewById(R.id.button2);
        Button btndiv = (Button) findViewById(R.id.button4);
        Button btnmul = (Button) findViewById(R.id.button3);
        final EditText etv = (EditText) findViewById(R.id.editTextNumber1);
        final EditText etv2 = (EditText) findViewById(R.id.editTextNumber2);
        final TextView result = (TextView) findViewById(R.id.textView1);

        btnsum.setOnClickListener(new View.OnClickListener() {

            @Override
            public void onClick(View v) {
                int x = new Integer(etv.getText().toString());
                int y = new Integer(etv2.getText().toString());
                int sum = x + y;
                result.setText( x + " + " + y + " = " + sum);
            }
        });

        btnsub.setOnClickListener(new View.OnClickListener() {

            @Override
            public void onClick(View v) {
                int x = new Integer(etv.getText().toString());
                int y = new Integer(etv2.getText().toString());
                int sub = x - y;
                result.setText( x + " - " + y + " = " + sub);
            }
        });

        btndiv.setOnClickListener(new View.OnClickListener() {

            @Override
            public void onClick(View v) {
                int x = new Integer(etv.getText().toString());
                int y = new Integer(etv2.getText().toString());
                double div = (float)x /(float) y;
                result.setText(x + " / " + y + " = " + div);
            }
        });

        btnmul.setOnClickListener(new View.OnClickListener() {

            @Override
            public void onClick(View v) {
                int x = new Integer(etv.getText().toString());
                int y = new Integer(etv2.getText().toString());
                int mul = x * y;
                result.setText(x + " * " + y + " = " + mul);
            }
        });


    }
}
```
## OUTPUT
![Screenshot 2022-05-28 135015](https://user-images.githubusercontent.com/75235601/170817266-8e702b39-42ff-4cbc-af5b-6c4c83c59ab7.jpg)
![Screenshot 2022-05-28 135048](https://user-images.githubusercontent.com/75235601/170817271-8201c416-a3e1-414c-891b-1c605b7f4d50.jpg)
![Screenshot 2022-05-28 135121](https://user-images.githubusercontent.com/75235601/170817274-bdfbb9bb-04aa-4d8a-95fb-2f09303d7fc5.jpg)
![Screenshot 2022-05-28 135138](https://user-images.githubusercontent.com/75235601/170817279-51aa2e11-f1ae-4f5c-b161-2f2cebd3b879.jpg)


## RESULT
Thus a Simple Android Application develop a program to create simple calculator in Android Studio is developed and executed successfully.
