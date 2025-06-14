# Documentation Development Guide

This repository contains the documentation for our project, built with Mintlify.

## Local Development

To run the documentation locally:

```bash
npx mint dev
```

This will start a local development server where you can preview changes in real-time.

## API Reference Management

Our API documentation follows a two-step process to provide better organization and flexibility:

### Overview

- **Source**: `openapi.yaml` - Contains the complete API specification
- **Generated Files**: MDX files in `./api-reference/` - Created from the OpenAPI spec
- **Configuration**: `docs.json` - References the generated MDX files for logical grouping

### Updating API Documentation

1. **Update the OpenAPI specification**:
   Edit `openapi.yaml` with your API changes

2. **Generate MDX files**:

   ```bash
   npx @mintlify/scraping@latest openapi-file openapi.yaml -o ./api-reference
   ```

3. **Update documentation structure**:
   Modify `docs.json` to reference the new MDX files as needed

### Why This Approach?

While Mintlify can use `openapi.yaml` directly, generating separate MDX files allows us to:

- Logically group related endpoints
- Customize the presentation of different API sections
- Maintain better control over the documentation structure
- Provide enhanced visual organization in the docs

## File Structure

```
├── openapi.yaml          # API specification source
├── api-reference/        # Generated MDX files
├── docs.json            # Documentation configuration
```
