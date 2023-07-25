# 0x01. Caching
![Back-end](data:image/jpeg;base64,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)

## Background Context

In this project, you learn different caching algorithms.

## Resources

Read or watch:

- [Cache replacement policies - FIFO](https://intranet.alxswe.com/rltoken/fjhr6EvFeF3mWwsPQXUKdQ)
- Cache replacement policies - LIFO](https://intranet.alxswe.com/rltoken/U44RQjXp8xBtsbNIyhHIyw)
- Cache replacement policies - LRU](https://intranet.alxswe.com/rltoken/gKerxvR4dnXQYkBX2ujZiQ)
- Cache replacement policies - MRU](https://intranet.alxswe.com/rltoken/Tmk4qEBZ7QTknvbpKabWfQ)
- Cache replacement policies - LFU]https://intranet.alxswe.com/rltoken/8PEJ8L34bxhL2y--BW5zGQ)

## Learning Objectives

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

## General

- What a caching system is
- What FIFO means
- What LIFO means
- What LRU means
- What MRU means
- What LFU means
- What the purpose of a caching system
- What limits a caching system have

## Requirements

### Python Scripts

- All your files will be interpreted/compiled on Ubuntu 18.04 LTS using python3 (version 3.7)
- All your files should end with a new line
- The first line of all your files should be exactly #!/usr/bin/env python3
- A README.md file, at the root of the folder of the project, is mandatory
- Your code should use the pycodestyle style (version 2.5)
- All your files must be executable
- The length of your files will be tested using wc
- All your modules should have a documentation (python3 -c 'print(__import__("my_module").__doc__)')
- All your classes should have a documentation (python3 -c 'print(__import__("my_module").MyClass.__doc__)')
- All your functions (inside and outside a class) should have a documentation (python3 -c 'print(__import__("my_module").my_function.__doc__)' and python3 -c 'print(__import__("my_module").MyClass.my_function.__doc__)')
- A documentation is not a simple word, it’s a real sentence explaining what’s the purpose of the module, class or method (the length of it will be verified)

## More Info

### Parent class BaseCaching

All your classes must inherit from BaseCaching defined below:

```
$ cat base_caching.py`
#!/usr/bin/python3`
""" BaseCaching module
"""

  class BaseCaching():
    """ BaseCaching defines:
      `- constants of your caching system
      - where your data are stored (in a dictionary)
    """
    MAX_ITEMS = 4

    def __init__(self):
        """ Initiliaze
        """
        self.cache_data = {}

    def print_cache(self):
        """ Print the cache
        """
        print("Current cache:")
        for key in sorted(self.cache_data.keys()):
            print("{}: {}".format(key, self.cache_data.get(key)))

    def put(self, key, item):
        """ Add an item in the cache
        """
        raise NotImplementedError("put must be implemented in your cache class")

    def get(self, key):
        """ Get an item by key
        """
        raise NotImplementedError("get must be implemented in your cache class")
```
