---
layout: page
title: "Chronicling America API Assignment"
description: Exploring Chronicling America's API
---

In this assignment, you are tasked with:
* searching Chronicling America's API for a key word of your choice
* parsing your results from a dictionary to a `DataFrame` with headings "title", "city", 'date", and "raw_text"
* processing the raw text by removing "\n" characters, stopwords, and then lemmatizing the raw text before adding it to a new column called "lemmas."
* saving your `DataFrame` to a csv file

If you need any help with this assignment please email micah.saxton@tufts.edu



```python
# imports
import requests
import json
import math
import pandas as pd
import spacy
```


```python
# initial search
url = 'https://chroniclingamerica.loc.gov/search/pages/results/?state=&date1=1777&date2=1963&proxtext=technology&x=0&y=0&dateFilterType=yearRange&rows=20&searchType=basic&format=json'
response = requests.get(url)
raw = response.text
results = json.loads(raw)
```


```python
# find total amount of pages
total_pages = math.ceil(results['totalItems'] / results['itemsPerPage'])
print(total_pages)
```

    4519



```python
# query the api and save to dict 
data = []
start_date = '1835'
end_date = '1853'
search_term = 'technology'
for i in range(1, total_pages+1):
    url = (f'https://chroniclingamerica.loc.gov/search/pages/results/?state=&date1={start_date}'
           f'&date2={end_date}&proxtext={search_term}&x=16&y=8&dateFilterType=yearRange&rows=20'
           f'&searchType=basic&format=json&page={i}')  # f-string
    response = requests.get(url)
    raw = response.text
    results = json.loads(raw)
    items_ = results['items']
    for item_ in items_:
        temp_dict = {}
        temp_dict['title'] = item_['title_normal']
        temp_dict['city'] = item_['city']
        temp_dict['date'] = item_['date']
        temp_dict['raw_text'] = item_['ocr_eng']
        data.append(temp_dict)
```


    ---------------------------------------------------------------------------

    KeyboardInterrupt                         Traceback (most recent call last)

    Input In [21], in <cell line: 6>()
          6 for i in range(1, total_pages+1):
          7     url = (f'https://chroniclingamerica.loc.gov/search/pages/results/?state=&date1={start_date}'
          8            f'&date2={end_date}&proxtext={search_term}&x=16&y=8&dateFilterType=yearRange&rows=20'
          9            f'&searchType=basic&format=json&page={i}')  # f-string
    ---> 10     response = requests.get(url)
         11     raw = response.text
         12     results = json.loads(raw)


    File ~/opt/anaconda3/lib/python3.9/site-packages/requests/api.py:75, in get(url, params, **kwargs)
         64 def get(url, params=None, **kwargs):
         65     r"""Sends a GET request.
         66 
         67     :param url: URL for the new :class:`Request` object.
       (...)
         72     :rtype: requests.Response
         73     """
    ---> 75     return request('get', url, params=params, **kwargs)


    File ~/opt/anaconda3/lib/python3.9/site-packages/requests/api.py:61, in request(method, url, **kwargs)
         57 # By using the 'with' statement we are sure the session is closed, thus we
         58 # avoid leaving sockets open which can trigger a ResourceWarning in some
         59 # cases, and look like a memory leak in others.
         60 with sessions.Session() as session:
    ---> 61     return session.request(method=method, url=url, **kwargs)


    File ~/opt/anaconda3/lib/python3.9/site-packages/requests/sessions.py:529, in Session.request(self, method, url, params, data, headers, cookies, files, auth, timeout, allow_redirects, proxies, hooks, stream, verify, cert, json)
        524 send_kwargs = {
        525     'timeout': timeout,
        526     'allow_redirects': allow_redirects,
        527 }
        528 send_kwargs.update(settings)
    --> 529 resp = self.send(prep, **send_kwargs)
        531 return resp


    File ~/opt/anaconda3/lib/python3.9/site-packages/requests/sessions.py:645, in Session.send(self, request, **kwargs)
        642 start = preferred_clock()
        644 # Send the request
    --> 645 r = adapter.send(request, **kwargs)
        647 # Total elapsed time of the request (approximately)
        648 elapsed = preferred_clock() - start


    File ~/opt/anaconda3/lib/python3.9/site-packages/requests/adapters.py:440, in HTTPAdapter.send(self, request, stream, timeout, verify, cert, proxies)
        438 try:
        439     if not chunked:
    --> 440         resp = conn.urlopen(
        441             method=request.method,
        442             url=url,
        443             body=request.body,
        444             headers=request.headers,
        445             redirect=False,
        446             assert_same_host=False,
        447             preload_content=False,
        448             decode_content=False,
        449             retries=self.max_retries,
        450             timeout=timeout
        451         )
        453     # Send the request.
        454     else:
        455         if hasattr(conn, 'proxy_pool'):


    File ~/opt/anaconda3/lib/python3.9/site-packages/urllib3/connectionpool.py:703, in HTTPConnectionPool.urlopen(self, method, url, body, headers, retries, redirect, assert_same_host, timeout, pool_timeout, release_conn, chunked, body_pos, **response_kw)
        700     self._prepare_proxy(conn)
        702 # Make the request on the httplib connection object.
    --> 703 httplib_response = self._make_request(
        704     conn,
        705     method,
        706     url,
        707     timeout=timeout_obj,
        708     body=body,
        709     headers=headers,
        710     chunked=chunked,
        711 )
        713 # If we're going to release the connection in ``finally:``, then
        714 # the response doesn't need to know about the connection. Otherwise
        715 # it will also try to release it and we'll have a double-release
        716 # mess.
        717 response_conn = conn if not release_conn else None


    File ~/opt/anaconda3/lib/python3.9/site-packages/urllib3/connectionpool.py:449, in HTTPConnectionPool._make_request(self, conn, method, url, timeout, chunked, **httplib_request_kw)
        444             httplib_response = conn.getresponse()
        445         except BaseException as e:
        446             # Remove the TypeError from the exception chain in
        447             # Python 3 (including for exceptions like SystemExit).
        448             # Otherwise it looks like a bug in the code.
    --> 449             six.raise_from(e, None)
        450 except (SocketTimeout, BaseSSLError, SocketError) as e:
        451     self._raise_timeout(err=e, url=url, timeout_value=read_timeout)


    File <string>:3, in raise_from(value, from_value)


    File ~/opt/anaconda3/lib/python3.9/site-packages/urllib3/connectionpool.py:444, in HTTPConnectionPool._make_request(self, conn, method, url, timeout, chunked, **httplib_request_kw)
        441 except TypeError:
        442     # Python 3
        443     try:
    --> 444         httplib_response = conn.getresponse()
        445     except BaseException as e:
        446         # Remove the TypeError from the exception chain in
        447         # Python 3 (including for exceptions like SystemExit).
        448         # Otherwise it looks like a bug in the code.
        449         six.raise_from(e, None)


    File ~/opt/anaconda3/lib/python3.9/http/client.py:1377, in HTTPConnection.getresponse(self)
       1375 try:
       1376     try:
    -> 1377         response.begin()
       1378     except ConnectionError:
       1379         self.close()


    File ~/opt/anaconda3/lib/python3.9/http/client.py:320, in HTTPResponse.begin(self)
        318 # read until we get a non-100 response
        319 while True:
    --> 320     version, status, reason = self._read_status()
        321     if status != CONTINUE:
        322         break


    File ~/opt/anaconda3/lib/python3.9/http/client.py:281, in HTTPResponse._read_status(self)
        280 def _read_status(self):
    --> 281     line = str(self.fp.readline(_MAXLINE + 1), "iso-8859-1")
        282     if len(line) > _MAXLINE:
        283         raise LineTooLong("status line")


    File ~/opt/anaconda3/lib/python3.9/socket.py:704, in SocketIO.readinto(self, b)
        702 while True:
        703     try:
    --> 704         return self._sock.recv_into(b)
        705     except timeout:
        706         self._timeout_occurred = True


    File ~/opt/anaconda3/lib/python3.9/ssl.py:1241, in SSLSocket.recv_into(self, buffer, nbytes, flags)
       1237     if flags != 0:
       1238         raise ValueError(
       1239           "non-zero flags not allowed in calls to recv_into() on %s" %
       1240           self.__class__)
    -> 1241     return self.read(nbytes, buffer)
       1242 else:
       1243     return super().recv_into(buffer, nbytes, flags)


    File ~/opt/anaconda3/lib/python3.9/ssl.py:1099, in SSLSocket.read(self, len, buffer)
       1097 try:
       1098     if buffer is not None:
    -> 1099         return self._sslobj.read(len, buffer)
       1100     else:
       1101         return self._sslobj.read(len)


    KeyboardInterrupt: 



```python
# convert dict to dataframe
df = pd.DataFrame.from_dict(data)
```


```python
# convert date column from string to date-time object
df['date'] = pd.to_datetime(df['date'])
```


```python
# sort by date
sorted_df = df.sort_values(by='date')
```


```python
# write function to process text
nlp = spacy.load("en_core_web_sm")

def process_text(text):
    text = text.replace('\n', ' ')
    doc = nlp(text)
    tokens = [token for token in doc]
    no_stops = [token for token in tokens if not token.is_stop]
    no_punct = [token for token in no_stops if token.is_alpha]
    lemmas = [token.lemma_ for token in no_punct]
    lemmas_lower = [lemma.lower() for lemma in lemmas]
    lemmas_string = ' '.join(lemmas_lower)
    return lemmas_string
```


```python
# apply process_text function to raw_text column
sorted_df['lemmas'] = sorted_df['raw_text'].apply(process_text)
```


```python
# save to csv
sorted_df.to_csv(f'../data/{search_term}{start_date}-{end_date}.csv', index=False)
```
