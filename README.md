# Function for a download Blob file.
## How to use:
### If you use Vue.js and vue-resource
#### In my case I'm using request service and interceptor.
```
/**
 * Interceptors help us to pre or post-processing a request,
 * it means we can modify the requests before it sent to the server or
 * we can modify the responses coming back from the request.
 * Interceptors are defined globally.
 *
 * @see {@link https://github.com/pagekit/vue-resource/blob/develop/docs/http.md#request-and-response-processing}
 */
Vue.http.interceptors.push((request, next) => {
  // modify request
  request.headers.set('Accept', 'application/pdf');
  request.responseType = 'blob';

  return (response) => {
    // modify response
    responce.body = '...';
  };
});
```

### Example:
```
fetchPromise
  .then((data) => downloadBlobFile(data, 'fileName', 'pdf'))
```
