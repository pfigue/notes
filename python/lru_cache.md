# LRU Caching of Functions

tags: python, cache, functions, lru

# Python 3

https://docs.python.org/3/library/functools.html#functools.lru_cache

# Python 2

[Cheeseshop: repoze.lru](https://pypi.python.org/pypi/repoze.lru/)

[Github: repoze.lru](https://github.com/repoze/repoze.lru)

Usage example:

    from repoze.lru import lru_cache  # http://stackoverflow.com/questions/11815873/memoization-library-for-python-2-7
    # or this in Py3: https://docs.python.org/3/library/functools.html#functools.lru_cache
    from geopy import geocoders


    class geogeo(object):

        def __init__(self):
            self.geoloc = geocoders.Nominatim()

        @lru_cache(maxsize=5000)  # Up to 5000 entries in the cache.
        def georeverse(self, coord):
            l = self.geoloc.reverse(coord)
            return l
            
    gg = geogeo()
    
    gg.georeverse(_FOOBAR)  # Will Geo reverse using an API.
    gg.georeverse(_FOOBAR)  # Will use the cached answer.

    # The cache lives inside the gg object.
