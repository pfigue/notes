tags: debug, python, traces

# Debugging with Traces

Cheatsheet:

    import logging
    
    # ...
    
    logging.basicConfig(level=logging.DEBUG)
    LOGGER = logging.getLogger(__name__)
    
    #...
    
    LOGGER.debug('foobar {}.'.format('blah'))



# Memory debugging

[27.7. tracemalloc — Trace memory allocations](https://docs.python.org/3/library/tracemalloc.html)

# Refs

1. [Logging HOWTO](https://docs.python.org/3.3/howto/logging.html)
2. [16.7. logging — Logging facility for Python](https://docs.python.org/3.3/library/logging.html)
