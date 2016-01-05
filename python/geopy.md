# Reverse geolocalization python

tags: python, geo, reverse, geopy

# Example

    from geopy import geocoders
    gl = geocoders.Nominatim()
    l = gl.reverse('49.44201,11.06535')  # lat, long format.
    print(l.address)
