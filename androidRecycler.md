# ANDROID RECYCLERVIEW  
[Home](./README.md)   
[Reference](https://developer.android.com/guide/topics/ui/layout/recyclerview#java)  

 The overall container for your user interface is a RecyclerView object that you add to your layout. The RecyclerView fills itself with views provided by a layout manager that you provide. You can use one of our standard layout managers (such as LinearLayoutManager or GridLayoutManager), or implement your own.  

 The views in the list are represented by view holder objects.   
 The view holder objects are managed by an adapter, which you create by extending RecyclerView.Adapter.  The adapter creates view holders as needed. The adapter also binds the view holders to their data. It does this by assigning the view holder to a position, and calling the adapter's onBindViewHolder() method.  

 ## Add the support library
 ```
 dependencies {
    implementation 'com.android.support:recyclerview-v7:28.0.0'
}
```

### Add recycler view to the layout file  
```
<?xml version="1.0" encoding="utf-8"?>
<!-- A RecyclerView with some commonly used attributes -->
<android.support.v7.widget.RecyclerView
    android:id="@+id/my_recycler_view"
    android:scrollbars="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"/>
```

### In the MyActivity
```
public class MyActivity extends Activity {
    private RecyclerView recyclerView;
    private RecyclerView.Adapter mAdapter;
    private RecyclerView.LayoutManager layoutManager;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.my_activity);
        recyclerView = (RecyclerView) findViewById(R.id.my_recycler_view);

        // use this setting to improve performance if you know that changes
        // in content do not change the layout size of the RecyclerView
        recyclerView.setHasFixedSize(true);

        // use a linear layout manager
        layoutManager = new LinearLayoutManager(this);
        recyclerView.setLayoutManager(layoutManager);

        // specify an adapter (see also next example)
        mAdapter = new MyAdapter(myDataset);
        recyclerView.setAdapter(mAdapter);
    }
    // ...
}
```
To feed all your data to the list, you must extend the RecyclerView.Adapter class. This object creates views for items, and replaces the content of some of the views with new data items when the original item is no longer visible.

The following code example shows a simple implementation for a data set that consists of an array of strings displayed using TextView widgets:

