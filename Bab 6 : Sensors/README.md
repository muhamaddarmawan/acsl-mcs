# BAB 6 - Acceleration, Light and Proximity Sensors

<img align="left" src="../images/logo.png" width="400">
<img align="left" src="../images/logo_ug.jpg" width="60">
<a href="https://github.com/lefalya">
  <img align="right" src="../images/Github.png" width="30">
</a>
<a href="https://www.linkedin.com/in/berninofalya/">
  <img align="right" src="../images/LinkedIn.png" width="30">
</a>
<img align="right" src="../images/BerninoFalya.png" width="200">
<br/><br/><br/><br/>

## Tujuan
Pada percobaan bab ini kalian akan memahamai cara mengakses sensor  akselerasi, jarak, serta cahaya yang tertanam pada perangkat Android kalian.

## Teori
### Accelerometer

## Codelab
1. Buatlah project baru pada Android Studio dengan kriteria sebagai berikut : 

| Field     | Isian |
| ---      | ---       |
| Nama Project  | **Sensors**   |
| Target & Minimum Target SDK  | **Phone and Tablet, API level 21**  |
| Tipe Activity | **Empty Activity** |
| Activity Name | **MainActivity** | 
| Language | **Java** |

2. Ganti keseluruhan kode pada `activity_main.xml` dengan kode berikut : 
```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/accelerometer"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="50dp"
        android:text="Accelerometer"
        android:textSize="12pt"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/lightSensor"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="50dp"
        android:text="Light Sensor"
        android:textSize="12pt"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/yAccVal" />

    <TextView
        android:id="@+id/proximity"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="50dp"
        android:text="proximity"
        android:textSize="12pt"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/lightVal" />

    <TextView
        android:id="@+id/accType"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="Type : "
        app:layout_constraintEnd_toEndOf="@+id/accelerometer"
        app:layout_constraintStart_toStartOf="@+id/accelerometer"
        app:layout_constraintTop_toBottomOf="@+id/accelerometer" />

    <TextView
        android:id="@+id/lightType"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="Type : "
        app:layout_constraintEnd_toEndOf="@+id/lightSensor"
        app:layout_constraintStart_toStartOf="@+id/lightSensor"
        app:layout_constraintTop_toBottomOf="@+id/lightSensor" />

    <TextView
        android:id="@+id/proxType"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="Type : "
        app:layout_constraintEnd_toEndOf="@+id/proximity"
        app:layout_constraintStart_toStartOf="@+id/proximity"
        app:layout_constraintTop_toBottomOf="@+id/proximity" />

    <TextView
        android:id="@+id/textView3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="X"
        app:layout_constraintEnd_toStartOf="@+id/accelerometer"
        app:layout_constraintTop_toBottomOf="@+id/accType" />

    <TextView
        android:id="@+id/textView4"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="Y"
        app:layout_constraintEnd_toEndOf="@+id/accType"
        app:layout_constraintStart_toStartOf="@+id/accType"
        app:layout_constraintTop_toBottomOf="@+id/accType" />

    <TextView
        android:id="@+id/textView5"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="Z"
        app:layout_constraintStart_toEndOf="@+id/accelerometer"
        app:layout_constraintTop_toBottomOf="@+id/accType" />

    <TextView
        android:id="@+id/xAccVal"
        android:layout_width="61dp"
        android:layout_height="18dp"
        android:layout_marginTop="16dp"
        android:text="TextView"
        app:layout_constraintEnd_toEndOf="@+id/textView3"
        app:layout_constraintStart_toStartOf="@+id/textView3"
        app:layout_constraintTop_toBottomOf="@+id/textView3" />

    <TextView
        android:id="@+id/yAccVal"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="TextView"
        app:layout_constraintEnd_toEndOf="@+id/textView4"
        app:layout_constraintStart_toStartOf="@+id/textView4"
        app:layout_constraintTop_toBottomOf="@+id/textView4" />

    <TextView
        android:id="@+id/zAccVal"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="TextView"
        app:layout_constraintEnd_toEndOf="@+id/textView5"
        app:layout_constraintStart_toStartOf="@+id/textView5"
        app:layout_constraintTop_toBottomOf="@+id/textView5" />

    <TextView
        android:id="@+id/lightVal"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="TextView"
        app:layout_constraintEnd_toEndOf="@+id/lightType"
        app:layout_constraintStart_toStartOf="@+id/lightType"
        app:layout_constraintTop_toBottomOf="@+id/lightType" />

    <TextView
        android:id="@+id/proxVal"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="TextView"
        app:layout_constraintEnd_toEndOf="@+id/proxType"
        app:layout_constraintStart_toStartOf="@+id/proxType"
        app:layout_constraintTop_toBottomOf="@+id/proxType" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

3. Tambahkan *dependencies* yang dibutuhkan pada kelas MainActivity.java dengan menuliskan baris-baris berikut : 
```java
package com.example.NAMA_PACKAGE;

import ...

import android.content.Context;
import android.hardware.Sensor;
import android.hardware.SensorEvent;
import android.hardware.SensorEventListener;
import android.hardware.SensorManager;
import android.os.Bundle;
import android.util.Log;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {
  
  @Override
  protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
  }
}
```

4. Tambahkan baris berikut untuk mendeklarasikan variable yang dibutuhkan. Variable `sensorManager` berfungsi sebagai representasi keseluruhan sensor yang tertanam pada perangkat Android. Variable `accSensor` berfungsi sebagai representasi sensor Accelerometer, `lightSensor` sebagai representasi sensor cahaya, dan `proximitySensor` sebagai representasi sensor jarak (*proximity*). Variable `accType` hingga `lightVal` berfungsi sebagai representasi `TextView` pada layout `activity_main`.

```java
package com.example.NAMA_PACKAGE;

import ...

...

public class MainActivity extends AppCompatActivity {
  
  private SensorManager sensorManager;
  private Sensor accSensor;
  private Sensor lightSensor;
  private Sensor proximitySensor;

  private TextView accType;
  private TextView lightType;
  private TextView proxType;
  private TextView xAccVal;
  private TextView yAccVal;
  private TextView zAccVal;
  private TextView proxVal;
  private TextView lightVal;
  
  @Override
  protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
  }
}
```

5. Selanjutnya tambahkan baris dibawah untuk melakukan *assingment* pada beberapa variable yang bertugas sebagai representasi `TextView` pada layout `activity_main`. 

```java
package com.example.NAMA_PACKAGE;

import ...

...

public class MainActivity extends AppCompatActivity {
  
  ...
  
  @Override
  protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        
        accType = findViewById(R.id.accType);
        lightType = findViewById(R.id.lightType);
        proxType = findViewById(R.id.proxType);
        xAccVal = findViewById(R.id.xAccVal);
        yAccVal = findViewById(R.id.yAccVal);
        zAccVal = findViewById(R.id.zAccVal);
        proxVal = findViewById(R.id.proxVal);
        lightVal = findViewById(R.id.lightVal);
  }
}
```
6. Lakukan implementasi `SensorEventListener` pada kelas `MainActivity` dengan menambahkan `implements SensorEventListener` pada akhir deklarasi kelas `MainActivity`.

7. Lakukan *assignment* pada variable `sensorManager`, `accSensor`, `lightSensor` dan `proximitySensor` dengan menambahkan baris berikut. Keluaran dari fungsi `sensorManager.getDefaultSensor` diperlukan oleh `accSensor`, `lightSensor` dan `proximitySensor` untuk mendapatkan representasi `Sensor` sesuai dengan tipe sensor yang diajukan melalui argumen fungsi. Sebagai contoh, variable `accSensor` membutuhkan representasi sensor akselerometer dengan memberikan argumen `Sensor.TYPE_ACCELEROMETER` ke fungsi `sensorManager.getDefaultSensor`. 
```java
package com.example.NAMA_PACKAGE;

import ...

...

public class MainActivity extends AppCompatActivity implements SensorEventListener {
  
  ...
  
  @Override
  protected void onCreate(Bundle savedInstanceState) {
         ...
         
        sensorManager = (SensorManager) getSystemService(Context.SENSOR_SERVICE);

        accSensor = sensorManager.getDefaultSensor(Sensor.TYPE_ACCELEROMETER);
        lightSensor = sensorManager.getDefaultSensor(Sensor.TYPE_LIGHT);
        proximitySensor = sensorManager.getDefaultSensor(Sensor.TYPE_PROXIMITY);
  }
}
```
