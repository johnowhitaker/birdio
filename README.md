# Birdio
> Work in progress, building a bird-call identification system.


This file will become your README and also the index of your documentation.

## Install

(Not set up yet)

`pip install your_project_name`

## How to use

Fill me in please! Don't forget code examples:

Querying Xeno Canto based on location:

```python
q =  query_box(-27, -25, 20, 25)
q['recordings'][0]
```


    ---------------------------------------------------------------------------

    KeyboardInterrupt                         Traceback (most recent call last)

    <ipython-input-5-4bc4ae3b928a> in <module>
    ----> 1 q =  query_box(-27, -25, 20, 25)
          2 q['recordings'][0]


    ~/Projects/birdsong/birdio/birdio/core.py in query_box(LAT_MIN, LAT_MAX, LON_MIN, LON_MAX)
          9 # Get the first page of results for a query on a given bounding box
         10 def query_box(LAT_MIN = -180, LAT_MAX = 180, LON_MIN = -180, LON_MAX = 180):
    ---> 11     response = requests.get(f'https://www.xeno-canto.org/api/2/recordings?query=box:{LAT_MIN},{LON_MIN},{LAT_MAX},{LON_MAX}')
         12     return response.json()
         13 


    ~/Apps/anaconda3/lib/python3.7/site-packages/requests/api.py in get(url, params, **kwargs)
         73 
         74     kwargs.setdefault('allow_redirects', True)
    ---> 75     return request('get', url, params=params, **kwargs)
         76 
         77 


    ~/Apps/anaconda3/lib/python3.7/site-packages/requests/api.py in request(method, url, **kwargs)
         58     # cases, and look like a memory leak in others.
         59     with sessions.Session() as session:
    ---> 60         return session.request(method=method, url=url, **kwargs)
         61 
         62 


    ~/Apps/anaconda3/lib/python3.7/site-packages/requests/sessions.py in request(self, method, url, params, data, headers, cookies, files, auth, timeout, allow_redirects, proxies, hooks, stream, verify, cert, json)
        531         }
        532         send_kwargs.update(settings)
    --> 533         resp = self.send(prep, **send_kwargs)
        534 
        535         return resp


    ~/Apps/anaconda3/lib/python3.7/site-packages/requests/sessions.py in send(self, request, **kwargs)
        644 
        645         # Send the request
    --> 646         r = adapter.send(request, **kwargs)
        647 
        648         # Total elapsed time of the request (approximately)


    ~/Apps/anaconda3/lib/python3.7/site-packages/requests/adapters.py in send(self, request, stream, timeout, verify, cert, proxies)
        447                     decode_content=False,
        448                     retries=self.max_retries,
    --> 449                     timeout=timeout
        450                 )
        451 


    ~/Apps/anaconda3/lib/python3.7/site-packages/urllib3/connectionpool.py in urlopen(self, method, url, body, headers, retries, redirect, assert_same_host, timeout, pool_timeout, release_conn, chunked, body_pos, **response_kw)
        598                                                   timeout=timeout_obj,
        599                                                   body=body, headers=headers,
    --> 600                                                   chunked=chunked)
        601 
        602             # If we're going to release the connection in ``finally:``, then


    ~/Apps/anaconda3/lib/python3.7/site-packages/urllib3/connectionpool.py in _make_request(self, conn, method, url, timeout, chunked, **httplib_request_kw)
        341         # Trigger any extra validation we need to do.
        342         try:
    --> 343             self._validate_conn(conn)
        344         except (SocketTimeout, BaseSSLError) as e:
        345             # Py2 raises this as a BaseSSLError, Py3 raises it as socket timeout.


    ~/Apps/anaconda3/lib/python3.7/site-packages/urllib3/connectionpool.py in _validate_conn(self, conn)
        837         # Force connect early to allow us to validate the connection.
        838         if not getattr(conn, 'sock', None):  # AppEngine might not have  `.sock`
    --> 839             conn.connect()
        840 
        841         if not conn.is_verified:


    ~/Apps/anaconda3/lib/python3.7/site-packages/urllib3/connection.py in connect(self)
        299     def connect(self):
        300         # Add certificate verification
    --> 301         conn = self._new_conn()
        302         hostname = self.host
        303 


    ~/Apps/anaconda3/lib/python3.7/site-packages/urllib3/connection.py in _new_conn(self)
        157         try:
        158             conn = connection.create_connection(
    --> 159                 (self._dns_host, self.port), self.timeout, **extra_kw)
        160 
        161         except SocketTimeout as e:


    ~/Apps/anaconda3/lib/python3.7/site-packages/urllib3/util/connection.py in create_connection(address, timeout, source_address, socket_options)
         68             if source_address:
         69                 sock.bind(source_address)
    ---> 70             sock.connect(sa)
         71             return sock
         72 


    KeyboardInterrupt: 


```python
1+1
```
