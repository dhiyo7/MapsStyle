# MapsStyle

Oke repo ini ditujukan untuk semua orang yang ingin membuat tampilan maps dengan suasana berbeda, mungkin saja dikarenakan bosan atau ingin membuat tampilan dark theme dengan maps style yang mengikuti color pallete dari aplikasinya.



### Alat

- [Google Maps SDK for Android](https://developers.google.com/maps/documentation/android-sdk/start)

- [Google Maps API key](https://developers.google.com/maps/documentation/android-sdk/get-api-key)

- [Custom Maps](https://snazzymaps.com/)



### Langkah langkah

1. Buat dulu class Maps.java, pada contoh disini saya implementasi pada Fragment, bukan Activity.



```java
private void setMapStyle() {

boolean result = mMap.setMapStyle(MapStyleOptions.loadRawResourceStyle(getActivity(), R.raw.maps_style));
        if (result){
            Log.e("MAP", "error set Map Style");
        }
    }

    @Override
    public void onMapReady(GoogleMap googleMap) {
        mMap = googleMap;
        float zoomLevel = 16.0f; //This goes up to 21
        LatLng tegal = new LatLng(-6.8694, 109.1402);
        mMap.addMarker(new MarkerOptions().position(tegal).title("Darurat"));
        mMap.moveCamera(CameraUpdateFactory.newLatLng(tegal));
        mMap.moveCamera(CameraUpdateFactory.newLatLngZoom(tegal, zoomLevel));
        setMapStyle();
    }
```

2. Buat folder "raw" pada resource kalian, kemudian tambahkan file (harus .json) karena style disini menggunakan json, nah file json nanti akan kalian isi dengan style yang sudah kalian cari pada web [https://snazzymaps.com/](https://snazzymaps.com/)
   
   contoh : maps_style.json



3. Kemudan copy paste saja json nya, contoh saya memlih [inturlam-style-2](https://snazzymaps.com/style/13005/inturlam-style-2) 
   
   ```json
   [
       {
           "featureType": "all",
           "elementType": "all",
           "stylers": [
               {
                   "invert_lightness": true
               },
               {
                   "saturation": 20
               },
               {
                   "lightness": 50
               },
               {
                   "gamma": 0.4
               },
               {
                   "hue": "#00ffee"
               }
           ]
       },
       {
           "featureType": "all",
           "elementType": "geometry",
           "stylers": [
               {
                   "visibility": "simplified"
               }
           ]
       },
       {
           "featureType": "all",
           "elementType": "labels",
           "stylers": [
               {
                   "visibility": "on"
               }
           ]
       },
       {
           "featureType": "administrative",
           "elementType": "all",
           "stylers": [
               {
                   "color": "#ffffff"
               },
               {
                   "visibility": "simplified"
               }
           ]
       },
       {
           "featureType": "administrative.land_parcel",
           "elementType": "geometry.stroke",
           "stylers": [
               {
                   "visibility": "simplified"
               }
           ]
       },
       {
           "featureType": "landscape",
           "elementType": "all",
           "stylers": [
               {
                   "color": "#405769"
               }
           ]
       },
       {
           "featureType": "water",
           "elementType": "geometry.fill",
           "stylers": [
               {
                   "color": "#232f3a"
               }
           ]
       }
   ]
   ```



4. Setelah itu tinggal kita Run hasilnya
   
  ![maps2](https://user-images.githubusercontent.com/25566307/69491684-d6e90700-0eca-11ea-9c96-8a326b62f59e.png)



Selesai 🥳 oke untuk lebih jelasnya silahkan cek Gist Berikut

- https://gist.github.com/dhiyo7/0f133971d439aa92c20b24e4cb9527dc

- https://gist.github.com/dhiyo7/dbf0c0e2813f73bd889ec85fc0719017



Jika ada yg kurang jelas silahkan PM saya melalu email yang ada di Profil 🐧
