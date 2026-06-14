# Database template reproduction

This is a reproduction of database template application using the repository's
existing, unchanged example:

```text
examples/templates/create-from.js
```

## Environment

- Upstream commit: `3ea8070593168c1e20ca08c6120ec8c5439481a8`
- `@notionhq/client`: `5.6.0`
- Test date: June 14, 2026
- Template argument: `default`
- No timezone argument
- No changes to the example or shared client code

## Command

Identifiers below are included so Notion can trace the requests. The
authentication token is not stored in this repository.

```bash
NOTION_API_TOKEN="$NOTION_TOKEN" node examples/templates/create-from.js \
  --dataSourceId=20c114e9-b09a-8284-9bba-0715e76d1532 \
  --template=default
```

## Result

The create call completed successfully and returned a normal page object:

- Page ID: `37f114e9-b09a-81e2-a579-fc93592136ce`
- Create request ID: `7a6f6463-60ec-4aff-a7b8-3638ca438b97`
- [Created page](https://app.notion.com/p/37f114e9b09a81e2a579fc93592136ce)

There was no API error or warning.

A later `Retrieve block children` request also completed successfully:

- Request ID: `1696176a-7302-4668-997d-0b66f4b6ec32`
- Response `results`: `[]`

The workspace-facing page fetch also reported that the page was blank and had
no content.

The page properties were created, but the default database template body was
not applied.
