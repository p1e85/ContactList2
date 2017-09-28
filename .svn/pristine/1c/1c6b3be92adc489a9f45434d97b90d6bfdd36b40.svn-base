package com.example.contactlist2;

import android.app.Activity;
import android.content.SharedPreferences;
import android.content.SharedPreferences.OnSharedPreferenceChangeListener;
import android.os.Bundle;
import android.preference.PreferenceManager;
import android.util.Log;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends Activity {

	String name, address, phone, email;
	EditText etName, etAddress, etPhone, etEmail;
	Button save, load, clear;

	@Override
	protected void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_main);

		SharedPreferences sp = PreferenceManager.getDefaultSharedPreferences(this);
		final SharedPreferences.Editor editor = sp.edit();

		etName = (EditText) findViewById(R.id.etName);
		etAddress = (EditText) findViewById(R.id.etAddress);
		etPhone = (EditText) findViewById(R.id.etPhone);
		etEmail = (EditText) findViewById(R.id.etEmail);

		save = (Button) findViewById(R.id.btnSave);
		load = (Button) findViewById(R.id.btnLoad);
		clear = (Button) findViewById(R.id.btnClear);

		save.setOnClickListener(new View.OnClickListener() {

			@Override
			public void onClick(View v) {
				SharedPreferences sp = getSharedPreferences("MY_PREFERENCES2",
						MODE_PRIVATE);

				name = etName.getText().toString();
				address = etAddress.getText().toString();
				phone = etPhone.getText().toString();
				email = etEmail.getText().toString();

				editor.putString("name", name);
				editor.putString("address", address);
				editor.putString("phone", phone);
				editor.putString("email", email);
				editor.commit();

				Toast.makeText(MainActivity.this, "Saved", Toast.LENGTH_LONG)
						.show();
			}
		});

		load.setOnClickListener(new View.OnClickListener() {

			@Override
			public void onClick(View v) {
				SharedPreferences sp = PreferenceManager
						.getDefaultSharedPreferences(MainActivity.this);

				String loadName, loadAddress, loadPhone, loadEmail;

				loadName = sp.getString("name", "Preference not found");
				etName.setText(loadName);
				loadAddress = sp.getString("address", "Preference not found");
				etAddress.setText(loadAddress);
				loadPhone = sp.getString("phone", "Preference not found");
				etPhone.setText(loadPhone);
				loadEmail = sp.getString("email", "Preference not found");
				etEmail.setText(loadEmail);

				// sp.edit().putString(KEY_1, val + "0").commit();

				Toast.makeText(MainActivity.this, "Loaded", Toast.LENGTH_LONG)
						.show();

			}
		});

		clear.setOnClickListener(new View.OnClickListener() {

			@Override
			public void onClick(View v) {
				Toast.makeText(MainActivity.this, "Cleared", Toast.LENGTH_LONG)
						.show();

				etName.setText("");
				etAddress.setText("");
				etPhone.setText("");
				etEmail.setText("");

			}
		});
	}

	@Override
	public boolean onCreateOptionsMenu(Menu menu) {
		// Inflate the menu; this adds items to the action bar if it is present.
		getMenuInflater().inflate(R.menu.main, menu);
		return true;
	}

	@Override
	public boolean onOptionsItemSelected(MenuItem item) {
		// Handle action bar item clicks here. The action bar will
		// automatically handle clicks on the Home/Up button, so long
		// as you specify a parent activity in AndroidManifest.xml.
		int id = item.getItemId();
		if (id == R.id.action_settings) {
			return true;
		}
		return super.onOptionsItemSelected(item);
	}
}
