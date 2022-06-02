# Kinesis
## location 
if you want to use location and maps to get the last location for users which is usually equivalent to the last known location of the device.
you need to use Google Play services location APIs 

- first step is to install Google Play services component via the SDK Manager and add the library to your project
- second step  request location permissions
- Create location services client
 ```
 private FusedLocationProviderClient fusedLocationClient;

// ..

@Override
protected void onCreate(Bundle savedInstanceState) {
    // ...

    fusedLocationClient = LocationServices.getFusedLocationProviderClient(this);
}
```

- Get the last known location
```
fusedLocationClient.getLastLocation()
        .addOnSuccessListener(this, new OnSuccessListener<Location>() {
            @Override
            public void onSuccess(Location location) {
                // Got last known location. In some rare situations this can be null.
                if (location != null) {
                    // Logic to handle location object
                }
            }
        });
```

in some times' location return null for multiple reasons like permission denied or The device never recorded its location

- Choose the best location estimate
  - getLastLocation() : gets a location estimate more quickly and minimizes battery usage that can be attributed to your app. However, the location information might be out of date, if no other clients have actively used location recently.
  - getCurrentLocation() : gets a fresher, more accurate location more consistently. However, this method can cause active location computation to occur on the device


resources

[location](https://developer.android.com/training/location/retrieve-current)