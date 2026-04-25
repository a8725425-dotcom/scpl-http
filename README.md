# HTTP Library for SCPL

Basic HTTP helpers built on top of the SCPL runtime.

## Exported Functions

- `http-request method url headers body timeout`
- `http-get url headers timeout`
- `http-post url body headers timeout`
- `http-ok? value`
- `http-error? value`
- `http-status value`
- `http-body value`
- `http-headers value`
- `http-json value`

## Usage

```scpl
import http
import test
Initialize-console

set: resp (http-get 'https://example.com' (dict) 10)
assert-ok: resp 'request succeeded'
Console-print: (http-status resp)
Console-print: (http-body resp)

Close-console
```

Results use the SCPL `ok/error` model. Successful responses unwrap to a dict with
`status`, `url`, `headers`, and `body`.
