---
title: Proxy-Authenticate
slug: Web/HTTP/Headers/Proxy-Authenticate
l10n:
  sourceCommit: 0b02491044c424c57fc7aff0c970164da602a72c
---

{{HTTPSidebar}}

Der HTTP-**`Proxy-Authenticate`**-{{Glossary("response_header", "Antwort-Header")}} definiert die [Authentifizierungsmethode](/de/docs/Web/HTTP/Authentication) (oder {{Glossary("Challenge", "Herausforderung")}}), die verwendet werden sollte, um Zugang zu einer Ressource hinter einem {{Glossary("proxy_server", "Proxy-Server")}} zu erlangen. Er wird in einer {{HTTPStatus("407", "407 Proxy Authentication Required")}}-Antwort gesendet, damit ein Client sich bei einem Proxy, der eine Authentifizierung erfordert, identifizieren kann.

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">Header-Typ</th>
      <td>{{Glossary("Response_header", "Antwort-Header")}}</td>
    </tr>
    <tr>
      <th scope="row">{{Glossary("Forbidden_header_name", "Verbotener Header-Name")}}</th>
      <td>Ja</td>
    </tr>
  </tbody>
</table>

## Syntax

```http
Proxy-Authenticate: <type> realm=<realm>
```

## Direktiven

- `<type>`
  - : [Authentifizierungstyp](/de/docs/Web/HTTP/Authentication#authentication_schemes).
    Ein häufiger Typ ist ["Basic"](/de/docs/Web/HTTP/Authentication#basic_authentication_scheme).
    IANA pflegt eine [Liste von Authentifizierungsschemata](https://www.iana.org/assignments/http-authschemes/http-authschemes.xhtml).
- `realm=<realm>`
  - : Eine Beschreibung des geschützten Bereichs, des Realm. Wenn kein Realm angegeben ist, zeigen Clients häufig stattdessen einen formatierten Hostnamen an.

## Beispiele

```http
Proxy-Authenticate: Basic

Proxy-Authenticate: Basic realm="Access to the internal site"
```

## Spezifikationen

{{Specifications}}

## Browser-Kompatibilität

{{Compat}}

## Siehe auch

- [HTTP-Authentifizierung](/de/docs/Web/HTTP/Authentication)
- {{HTTPHeader("Authorization")}}, {{HTTPHeader("Proxy-Authorization")}}
- {{HTTPHeader("WWW-Authenticate")}}
- {{HTTPStatus("401")}}, {{HTTPStatus("403")}}, {{HTTPStatus("407")}}
