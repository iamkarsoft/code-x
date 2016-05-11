### adding launcher icon

* app > new image asset > choose image *

### creating a text view 

```
<TextView
	
	//creating an id 
	android:id="@+id/list_item_forecast"

	//layout width and height

	android:layout_width="match_parent"
	android:layout_heigh="wrap_content"


/>

```


### Layouts

responsive design

- Frame layout 
great for simple layout like a list view 

- linear layout 
good stacking views vertically or horizontally 

- relative layout 
Powerful but more difficult


### creating data using array 

```
   String[] forecastArray = {
                    "Today - Sunny - 88/83 ",
                    "Tomorrow - Foggy - 70/40 ",
                    "Friday - Cloudy - 75/83 ",
                    "Sat - Sunny - 88/83 ",
                    "Sun - Help Trapped in WeatherStation - 70/40 ",
                    "Friday - Cloudy - 75/83 "
            };

```

### initializing adapter

- Parameters
 -- context  ``` getActivity() ```
 -- Id of list item layout ``` R.layout.list_item_forecast ```
 -- Id of text view  ``` R.id.list_item_forecast_textview ```
 -- list of data week Forecast 

 full code 

 ```     //declaring array adapter

            mForecastAdapter =
                    new ArrayAdapter<String>(

                            getActivity(),
                            //id of list item layout
                            R.layout.list_item_forcast,
                            //id of the textview
                            R.id.list_item_forecast_textview,
                            //forecast data
                            weekForecast
                    );
```




