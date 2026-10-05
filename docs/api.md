# API

The authoritative contract is
[`openapi.yaml`](https://github.com/Dhanushsingamala/nikhil-node-service/blob/main/openapi.yaml),
served live at `GET /openapi.yaml` and rendered in Backstage on the **API** tab
of `nikhil-rest-apiservice-api`.

## Endpoints

| Method | Path | Purpose | Success |
|---|---|---|---|
| `GET` | `/health` | Liveness and readiness probe | `200` |
| `GET` | `/openapi.yaml` | This service's OpenAPI document | `200` |
| `GET` | `/books` | List books | `200` |

## Errors

Every error uses the same envelope. Stack traces are never returned.

```json
{
  "error": { "code": "NOT_FOUND", "message": "..." }
}
```

| Code | Status |
|---|---|
| `NOT_FOUND` | 404 |
| `INTERNAL_ERROR` | 500 |

## Not implemented

No authentication, authorization, rate limiting or persistence. Add them
before this service handles anything real.
