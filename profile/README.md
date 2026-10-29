<h1><img src="https://raw.githubusercontent.com/kiss-gym/.github/main/pictures/org-logo02.png" alt="Kiss Gym logo" width="40" height="40" align="center"> &nbsp;Kiss Gym</h1>

A gym training tracker focused on simplicity and flexibility. Start a session from
the previous exercise sequence and adapt it as you train.

## Key Components

| Repository | Tech | Description |
|-----------|------|-------------|
| [gym-api](https://github.com/kiss-gym/gym-api) | C# / ASP.NET Core | REST API for training sessions, exercises and user management; Supabase for data and authentication |
| [gym-andr](https://github.com/kiss-gym/gym-andr) | TypeScript / React Native / Expo | Primary Android client for tracking training sessions |

## Architecture Overview

```mermaid
flowchart TD

classDef dottedBox fill:transparent,fill-opacity:0.55,stroke-dasharray:20 5,stroke-width:2px;

android["gym-andr<br>(React Native / Expo Android)"]
api["gym-api<br>(ASP.NET Core REST API)"]

subgraph supabase["Supabase"]
    postgres[("PostgreSQL")]
    auth["Supabase Auth"]
end
class supabase dottedBox

android -->|REST requests| api
api -->|Persistence via EF Core| postgres
api -->|JWT validation via JWKS| auth
```

## License

[MIT](https://github.com/kiss-gym/.github/blob/main/LICENSE)

## Contact

Eduard Danziger<br>
[github.com/eduarddanziger](https://github.com/eduarddanziger)
