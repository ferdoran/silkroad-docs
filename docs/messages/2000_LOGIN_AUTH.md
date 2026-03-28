# LOGIN_AUTH

| Property | Value |
|----------|-------|
| Opcode | `0x2000` |
| Direction | Client → Server |
| Group | Login |
| Handler(s) | `0x008832A0` |
| Binary | GatewayServer.exe |

### Overview

The `0x2000 LOGIN_AUTH` packet is sent by the client to the GatewayServer carrying
login credentials. The GatewayServer processes it by:

1. URL-escaping the extracted username and password
2. Calling Yahoo's authentication API:
   `http://login.korea.yahoo.com/config/isp_verify_user?.src=mmo&l=%s&p=%s`
3. Parsing the response (`OK:0`, `NOMAIL:0`, `Invalid Password`, etc.)

This confirms the payload contains at minimum a **username** and **password** field.

### Fields

| # | Name | Type | Description |
|---|------|------|-------------|
| 1 | `Username` | `ascii` | Login username (URL-escaped by gateway) |
| 2 | `Password` | `ascii` | Login password (URL-escaped by gateway) |

> Additional fields (client locale, version token, etc.) may be present.
> The exact layout was not extractable from static analysis of the gateway binary
> because credentials are read via a framework-level packet reader, not via
> traceable `WriteField` calls.

### Binary Evidence

GatewayServer.exe, `fcn.00414a90` (receive handler for `0x2000`):

```c
// Credentials extracted from incoming packet into auStack_914 and auStack_814
iVar2 = fcn.0040c950(
    "http://login.korea.yahoo.com/config/isp_verify_user?.src=mmo&l=%s&p=%s",
    auStack_414,   // username buffer
    auStack_914    // password buffer
);
```

> Note: The value `0x2000` (8192) also appears as buffer sizes in the gateway's
> HTTP response buffers — those occurrences are **not** the protocol opcode.
