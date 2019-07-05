# Requests III: HTTP for Humans and Machines, alike.

<a href="https://travis-ci.org/encode/http3" style="text-decoration: none">
    <img src="https://travis-ci.org/encode/http3.svg?branch=master" alt="Build Status">
</a>
<a href="https://codecov.io/gh/encode/http3" style="text-decoration: none">
    <img src="https://codecov.io/gh/encode/http3/branch/master/graph/badge.svg" alt="Coverage">
</a>
<a href="https://pypi.org/project/http3/" style="text-decoration: none">
    <img src="https://badge.fury.io/py/http3.svg" alt="Package version">
</a>

**Requests III** is an HTTP library for Python, built for Humans and Machines, alike. **This repository is a work in progress, and the expected release timeline is “before PyCon 2020”.**

---

Behold, the power of Requests III:

```python
>>> import requests3
>>> r = requests3.get('https://www.example.org/')
>>> r
<Response [200 OK]>
>>> r.status_code
200
>>> r.protocol
'HTTP/2'
>>> r.headers['content-type']
'text/html; charset=UTF-8'
>>> r.text
'<!doctype html>\n<html>\n<head>\n<title>Example Domain</title>...'
```

## Features

Requests III is ready for today’s web.

* HTTP/2 and HTTP/1.1 support.
* Support for [issuing HTTP requests in parallel](parallel.md). *(Coming soon)*
* Standard synchronous interface, but [with `async`/`await` support if you need it](async.md).
* Ability to [make requests directly to WSGI or ASGI applications](advanced.md#calling-into-python-web-apps).
* Strict timeouts everywhere.
* Fully type annotated.
* 100% test coverage.

While retaining all the features of [Requests Classic](https://2.python-requests.org/):

* International Domains and URLs
* Keep-Alive & Connection Pooling
* Sessions with Cookie Persistence
* Browser-style SSL Verification
* Basic/Digest Authentication *(Digest is still TODO)*
* Elegant Key/Value Cookies
* Automatic Decompression
* Automatic Content Decoding
* Unicode Response Bodies
* Multipart File Uploads
* HTTP(S) Proxy Support *(TODO)*
* Connection Timeouts
* Streaming Downloads
* .netrc Support *(TODO)*
* Chunked Requests

## The User Guide

This part of the documentation, which is mostly prose, focuses on step-by-step instructions for getting the most out of Requests III.

<a class="reference internal" href="quickstart/">Quickstart</a><ul>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#make-a-request">Make a Request</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#passing-parameters-in-urls">Passing Parameters In URLs</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#response-content">Response Content</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#binary-response-content">Binary Response Content</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#json-response-content">JSON Response Content</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#custom-headers">Custom Headers</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#sending-form-encoded-data">Sending Form Encoded Data</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#sending-multipart-file-uploads">Sending Multipart File Uploads</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#sending-json-encoded-data">Sending JSON Encoded Data</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#response-status-codes">Response Status Codes</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#response-headers">Response Headers</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#cookies">Cookies</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#redirection-and-history">Redirection and History</a></li>
<li class="toctree-l2"><a class="reference internal" href="quickstart/#timeouts">Timeouts</a></li>
</ul>

<a class="reference internal" href="advanced/">Advanced Usage</a><ul>
<li class="toctree-l2"><a class="reference internal" href="advanced/#client-instances">Client Instances</a></li>
<li class="toctree-l2"><a class="reference internal" href="advanced/#calling-into-python-web-apps">Calling into Python Web Apps</a></li>
</ul>

<a class="reference internal" href="parallel/">Parallel Requests</a><ul>
<li class="toctree-l2"><a class="reference internal" href="parallel/#making-parallel-requests">Making Parallel Requests</a></li>
<li class="toctree-l2"><a class="reference internal" href="parallel/#exceptions-and-cancellations">Exceptions and Cancellations</a></li>
<li class="toctree-l2"><a class="reference internal" href="parallel/#parallel-requests-with-a-client">Parallel requests with a Client</a></li>
<li class="toctree-l2"><a class="reference internal" href="parallel/#async-parallel-requests">Async parallel requests</a></li>
</ul>

<a class="reference internal" href="async/">Async Client</a><ul>
<li class="toctree-l2"><a class="reference internal" href="async/#making-async-requests">Making Async Requests</a></li>
<li class="toctree-l2"><a class="reference internal" href="async/#async-parallel-requests">Async parallel requests</a></li>
</ul>

## The API Guide

The [Developer Interface](api.md) provides a comprehensive API reference.

The [Compatibility Guide](compatibility.md) provides a reference point for API
differences between the `requests` and `requests3` packages, and so serve as
a reference point for migrating existing projects to Requests III.

## Credits

Designed & Authored by Tom Christie & Kenneth Reitz.

Requests III relies on these excellent libraries:

* `h2` - HTTP/2 support.
* `h11` - HTTP/1.1 support.
* `certifi` - SSL certificates.
* `chardet` - Fallback auto-detection for response encoding.
* `idna` - Internationalized domain name support.
* `rfc3986` - URL parsing & normalization.
* `brotlipy` - Decoding for "brotli" compressed responses. *(Optional)*
