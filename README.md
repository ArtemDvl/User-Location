# User-LocationОпределение местоположения пользователя.

Это приложение получает местоположение пользователя и передает его на дисплей с помощью MapKit и CoreLocation 🗺

## Пример использования CLLocationManager:


func locationManager(_ manager: CLLocationManager, didUpdateLocations locations: [CLLocation])
{
    let location = locations[0]
    
    let span:MKCoordinateSpan = MKCoordinateSpanMake(0.01, 0.01)
    let myLocation:CLLocationCoordinate2D = CLLocationCoordinate2DMake(location.coordinate.latitude, location.coordinate.longitude)
    let region:MKCoordinateRegion = MKCoordinateRegionMake(myLocation, span)
    map.setRegion(region, animated: true)
    
    print(location.altitude)
    print(location.speed)
    
    self.map.showsUserLocation = true
}

