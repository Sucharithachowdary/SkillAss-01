# SkillAss-01
Develop a program to create a Thread using Android Studio
## AIM:

Develop a program to create a Thread using Android Studio

## EQUIPMENTS REQUIRED:




## ALGORITHM:



## Program:


## MainActivity.java:
```
import android.os.AsyncTask;
import android.os.Bundle;
import android.widget.Button;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

	private TextView resultTextView;

	@Override
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_main);

		// Get reference to start button and result text view
		Button startButton = findViewById(R.id.start_button);
		resultTextView = findViewById(R.id.result_text_view);
		
		// Set an OnClickListener for the start button
		startButton.setOnClickListener(view -> new BackgroundTask().execute());
	}

	// BackgroundTask inner class to perform the background task
	private class BackgroundTask extends AsyncTask<Void, Void, String> {
		@Override
		protected String doInBackground(Void... voids) {
			// Perform background task
			try {
				Thread.sleep(5000);
			} catch (InterruptedException e) {
				e.printStackTrace();
			}
			return "Task Completed";
		}

		@Override
		protected void onPostExecute(String result) {
			// Update UI with the results
			resultTextView.setText(result);
		}
	}
}


```

## activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
	xmlns:android="http://schemas.android.com/apk/res/android"
	android:layout_width="match_parent"
	android:layout_height="match_parent"
	android:gravity="center"
	android:orientation="vertical">

	<!-- Display the result text -->
	<TextView
		android:id="@+id/result_text_view"
		android:layout_width="wrap_content"
		android:layout_height="wrap_content"
		android:text="Result will appear here"
		android:textSize="25sp" />

	<!-- Start button -->
	<Button
		android:id="@+id/start_button"
		android:layout_width="wrap_content"
		android:layout_height="wrap_content"
		android:text="Start" />
	
</LinearLayout>
```

## Output
![output]()



## Result:

