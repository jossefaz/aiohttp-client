# Async HTTP Client : Getting started

---

## Introduction

When building a service oriented architecture, we often need a dedicated part of our program for external communication.
This is the role of the HTTP Client.

However, the relatively new way of asynchronous programming which improve dramatically the performance by giving control back to the main thread on each new single asynchronous task, 
force us to program in an asynchronous way along all each incoming request (if this one started as asynchronous, we must continue it, otherwise the main thread will be blocked again).

This library provides a simple class that manage the HTTP communication in an asynchronous way.

### First Step : Install it

```shell
pip install async_http_client
```

### Second Step : Import it

```python
from async_http_client import async_client_factory

client = async_client_factory(host="example.com", port=8080, protocol="https")
```

### Third Step : Use it

```python
async def get_my_resource(dummy_id):
    return await client().get(f"/{dummy_id}")
```
 
Since client is a factory, we need to call it (notice the `client()` syntaxe here) on every use (for further explanation, check API Reference

