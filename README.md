# ENACTUSR2

#ENACTUS TECH PROJECT ROUND 2 MADE BY=== KRISHNA AGARWAL, ROLL NO== 2024UCM2363

CODE===

package com.example.irrigationsystem;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    private TextView soilMoistureTextView;
    private TextView weatherTextView;
    private TextView irrigationStatusTextView;
    private Button fetchDataButton;

    // examples for soil moisture and water
    private double soilMoistureLevel = 35.0;
    private String weatherReport = "Sunny";
    private boolean isIrrigationOn = false;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        soilMoistureTextView = findViewById(R.id.soilMoistureTextView);
        weatherTextView = findViewById(R.id.weatherTextView);
        irrigationStatusTextView = findViewById(R.id.irrigationStatusTextView);
        fetchDataButton = findViewById(R.id.fetchDataButton);
        updateUI();

        // Fetch data when button is clicked
        fetchDataButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                fetchData();
            }
        });
    }

    //the methods to stimullate the data
    private void fetchData() {
        //stimulate the data
        soilMoistureLevel = 40.0;  // Update with new soil moisture level
        weatherReport = "Cloudy";  // Update with new weather report
        isIrrigationOn = soilMoistureLevel < 50.0;  // Example logic to turn irrigation on/off

        updateUI();
    }

    private void updateUI() {
        soilMoistureTextView.setText("Soil Moisture Level: " + soilMoistureLevel + "%");
        weatherTextView.setText("Weather Report: " + weatherReport);
        irrigationStatusTextView.setText("Irrigation Status: " + (isIrrigationOn ? "On" : "Off"));
        irrigationStatusTextView.setTextColor(isIrrigationOn ? getResources().getColor(R.color.green) : getResources().getColor(R.color.red));
    }
}



<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:id="@+id/soilMoistureTextView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Soil Moisture Level: 35%"
        android:textSize="20sp" />

    <TextView
        android:id="@+id/weatherTextView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Weather Report: Sunny"
        android:textSize="20sp"
        android:layout_marginTop="10dp" />

    <TextView
        android:id="@+id/irrigationStatusTextView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Irrigation Status: Off"
        android:textSize="20sp"
        android:layout_marginTop="10dp"
        android:textColor="@android:color/holo_red_dark" />

    <Button
        android:id="@+id/fetchDataButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Fetch Latest Data"
        android:layout_marginTop="20dp" />
</LinearLayout>



-------------------------------------------------------------------------------------THE END----------------------------------------------------------------------------------------------
# P.S. - I wasn't able to fully accomodate all the details provided to us but I have incorporated what I can. 
