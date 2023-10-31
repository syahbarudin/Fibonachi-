# Fibonachi-

#layout Main Activity

    <?xml version="1.0" encoding="utf-8"?>
    <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/button_toast"
        android:layout_width="421dp"
        android:layout_height="48dp"
        android:layout_marginTop="4dp"
        android:background="@color/colorPrimary"
        android:onClick="showToast"
        android:text="Toast"
        android:textColor="@android:color/white"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <Button
        android:id="@+id/button2"
        android:layout_width="204dp"
        android:layout_height="wrap_content"
        android:background="@color/colorPrimary"
        android:onClick="countUp"
        android:text="@string/button_label_count"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.99"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/back"
        android:layout_width="204dp"
        android:layout_height="wrap_content"
        android:background="@color/colorPrimary"
        android:onClick="Back"
        android:text="@string/Back"
        android:textColor="@android:color/white"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        tools:ignore=",Rtlcompat"/>

    <TextView
        android:id="@+id/show_count"
        android:layout_width="407dp"
        android:layout_height="626dp"
        android:background="#FFFF00"
        android:gravity="center_vertical"
        android:text="1"
        android:textAlignment="center"
        android:textColor="@color/colorPrimary"
        android:textSize="160sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@+id/button2"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/button_toast"
        tools:ignore=",Rtlcompat" />

</androidx.constraintlayout.widget.ConstraintLayout>

#Main Activity Java

    package com.example.toast;
    
    import android.os.Bundle;
    import android.view.View;
    import android.widget.TextView;
    import android.widget.Toast;
    
    import androidx.appcompat.app.AppCompatActivity;
    
    public class MainActivity extends AppCompatActivity {
        private int count = 1;
        private TextView showCount;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        showCount = findViewById(R.id.show_count);
    }

    public void showToast(View view) {
        Toast toast = Toast.makeText(this, "Hello Toast!", Toast.LENGTH_SHORT);
        toast.show();
    }

    public void countUp(View view) {
        if (count < 0) {
            count = 0;
        }

        int result = generateFibonacci(count);

        if (result <= 200) {
            showCount.setText(Integer.toString(result));
            count++;
        }}

    private int generateFibonacci(int n) {
        if (n <= 0) {
            return 0;
        } else if (n == 1) {
            return 1;
        }

        int first = 0;
        int second = 1;

        for (int i = 2; i <= n; i++) {
            int next = first + second;
            first = second;
            second = next;
        }

        return second;
    }

    public void Back(View view) {
        count = 1;
        showCount.setText("1");}

}

#String

    <resources>
        <string name="app_name">Toast</string>
        <string name="button_label_toast">Toast</string>
        <string name="button_label_count">Count</string>
        <string name="count_initial_value">0</string>
        <string name="coast_message">Hello Toast</string>
        <string name="Back">kembali</string>
    </resources>


#hasil program dalam bentuk video

https://github.com/syahbarudin/Fibonachi-/assets/146621192/bc64c4fb-03f9-4aa6-930b-c4412fca47a1

