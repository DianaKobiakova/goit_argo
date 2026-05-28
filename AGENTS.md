It's argocd project playground.


# Variables

in .env varialbe next to the @AGENTS.md is placed the following variables:
- ARGOCD_TOKEN
- ARGOCD_USERNAME
- ARGOCD_PASSWORD


# Tools

Use curl as base instrument.

- To get ARGOCD_TOKEN: 
```
source .env && curl -X POST -H "Content-Type: application/json" \
  -d "{\"username\":\"$ARGOCD_USERNAME\",\"password\":\"$ARGOCD_PASSWORD\"}" \
  http://localhost:8080/api/v1/session
```

Each command should use .env variables, e.g.:
```
source .env && curl -H "Authorization: Bearer $ARGOCD_TOKEN" \
  http://localhost:8080/api/v1/applications
```

# Useful documentations

- Official ARGOCD API DOC: https://cd.apps.argoproj.io/swagger-ui