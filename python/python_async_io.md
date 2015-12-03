Python Async I/O

tags: python, async

Twisted: can use iocp, twisted, etc.
Tornado: epolls in Unix, select in Windows.
Gevent: libevent but select() in Windows. greenlet.
Asyncore: begin of python3 async i/o
tulip/asyncio: Tulip was the former name.
  * ideally Twisted reactors could use asyncio as eventloop. Also Tornado and Gevents.

[selectors – High-level I/O multiplexing](https://docs.python.org/3/library/selectors.html): OS-independent I/O multiplexers (select, epoll, iocp, etc.)
[Youtube - PEP-3156: IO Asyncrona en Python. ¿Cómo funciona un event loop? (PyConES 2013), Saúl Ibarra Corretgé](https://www.youtube.com/watch?v=pkVcvRBq_xc)
