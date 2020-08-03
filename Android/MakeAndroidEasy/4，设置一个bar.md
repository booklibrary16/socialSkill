1,特别需要注意的是navigation。   


<android.support.v7.widget.Toolbar xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/id_toolbar"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:background="#000000"
    app:navigationIcon="@drawable/back"
    app:titleTextColor="#ffffff" />
    
    
        protected void setUpToolbar() {
        Toolbar toolbar = (Toolbar) findViewById(R.id.id_toolbar);
        setSupportActionBar(toolbar);

        toolbar.setNavigationOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                onBackPressed();
            }
        });

    }
    
