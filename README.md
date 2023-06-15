# SkillAss-01
Develop a program to create a Thread using Android Studio
## AIM:

Develop a program to create a Thread using Android Studio

## EQUIPMENTS REQUIRED:
Android Studio(Min. required Artic Fox)

## ALGORITHM:
Step 1: Open Android Studio and then click on File -> New -> New project.

Step 2: Then type the Application name as SMSIntent and click Next.

Step 3: Select the Minimum SDK below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally, click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Thread processing is done in MainActivity.java

Step 7: Save and run the application.


## Program:
```
Develped by : k sucharitha
Reg no : 212221240021
```


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
Thus a Simple Android Application to create an Thread using Android Studio was developed and executed successfully.
