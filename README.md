# myBestTimerOnTheWorld
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity" >

    <Button
        android:id="@+id/button1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:onClick="onClick"
        android:text="Button ME" />

    <FrameLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:padding="30dp" >

        <Button
            android:id="@+id/bubble_button"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:background="@drawable/dark_button"
            android:text="Mouse count"
            android:textColor="#FFFFFF" />

        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="right"
            android:layout_marginRight="2dp"
            android:layout_marginTop="2dp"
            android:background="@drawable/count_bubble"
            android:gravity="center"
            android:padding="4dp" >

            <TextView
                android:id="@+id/tvNotification"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="00"
                android:textColor="#FFFFFF"
                android:textSize="4pt"
                android:textStyle="bold" />
        </LinearLayout>
    </FrameLayout>

</LinearLayout>

?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item
            android:state_pressed="false"
            android:state_enabled="true"
            android:drawable="@drawable/dark_button_up"/>
    <item
            android:state_enabled="false"
            android:drawable="@drawable/dark_button_up" />
    <item
            android:state_pressed="true"
            android:state_enabled="true"
            android:drawable="@drawable/dark_button_dn"/>
    <item
            android:state_focused="true"
            android:state_enabled="true"
            android:drawable="@drawable/dark_button_up"/>
</selector>

<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle" >

    <gradient
        android:angle="90"
        android:endColor="#ffa800"
        android:startColor="#df8e00" />

    <padding
        android:bottom="15dp"
        android:left="9dp"
        android:right="9dp"
        android:top="15dp" />

    <corners android:radius="10dp" />

</shape>

<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle" >

    <gradient
        android:angle="90"
        android:endColor="#f5343b"
        android:startColor="#b30e13" />

    <padding
        android:bottom="3dp"
        android:left="9dp"
        android:right="9dp"
        android:top="3dp" />

    <stroke
        android:width="2dp"
        android:color="#ffffff" />

    <corners android:radius="10dp" />

</shape>

protected void onCreate(Bundle savedInstanceState) {
	super.onCreate(savedInstanceState);
	setContentView(R.layout.activity_main);

	Button bubbleButton = (Button) findViewById(R.id.bubble_button);
	final TextView tvNotification = (TextView)findViewById(R.id.tvNotification);

	bubbleButton.setOnClickListener(new View.OnClickListener() {
		int pressedTimes = 0;

		@Override
		public void onClick(View view) {
			tvNotification.setText(String.valueOf(pressedTimes));
		}
	});
}
