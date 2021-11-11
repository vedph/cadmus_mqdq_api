# Cadmus MQDQ API

Quick Docker image build:

```bash
docker build . -t vedph2020/cadmus_mqdq_api:2.0.0 -t vedph2020/cadmus_mqdq_api:latest
```

(replace with the current version).

This is a Cadmus API layer customized for the MQDQ (Musisque Deoque) project. Most of its code is derived from shared Cadmus libraries. See the [documentation](https://github.com/vedph/cadmus_doc/blob/master/api/creating.md) for more.

## History

- 2021-11-11: upgraded to NET 6.

- 2021-11-06: updated packages.

- 2021-10-15 (v 1.1.0): minor breaking change for auth database by AspNetCore.Identity.Mongo 8.3.1 (used since Cadmus.Api.Controllers 1.3.0, Cadmus.Api.Services 1.2.0):

```js
/*
Removed fields:
AuthenticatorKey = null
RecoveryCodes = []
*/
db.Users.updateMany({}, { $unset: {"AuthenticatorKey": 1, "RecoveryCodes": 1} });
```
