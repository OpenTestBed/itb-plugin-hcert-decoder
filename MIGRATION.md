From WHO-ITB/gdhcn-helper:
1. Move app.py, src/, Dockerfile*, requirements.txt here; keep git history if practical.
2. Wrap existing Flask endpoints (/decode/image, /decode/hcert, /vhl/...) with the GITB
   REST contract at /itb/hcert (getModuleDefinition, process ops decodeImage/decodeHcert/
   resolveShlink, begin/endTransaction no-ops) — follow org.hl7.fhir.core itb-rest-spec.md.
3. Publish GHCR image on tag; drop `build:` from all deployments.
4. Starter suite from WHO-ITB test-data QRs (known-good decodes, NO_PIN fails PIN flow).
