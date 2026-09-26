# YouTok — AWS Serverless Media Page

An experimental serverless web page that combines randomized YouTube playback with streaming radio.

**Live endpoint:** [Open YouTok](https://x86yytftfh.execute-api.us-east-1.amazonaws.com/default/generateYoutubeLink)

## Features

- Embedded YouTube video player
- Random video and radio selection
- Refresh through the page control, mouse wheel, or browser reload
- Static HTML/CSS/JavaScript interface
- AWS Lambda-backed serverless delivery

## Repository contents

- `AWS_lambda_function.txt` — Lambda function source/reference
- `index(local test).html` — local browser version
- `README.md` — project documentation

## Architecture

A request reaches an AWS endpoint backed by Lambda, which returns the page and media-selection behavior. The project is intentionally small and demonstrates a serverless alternative to a continuously running web server.

## Local review

Serve the repository root with a static server and open the local HTML file:

```bash
python -m http.server 8000
```

## Notes

External YouTube, radio, and API endpoints can change or become unavailable. For a production version, move media sources into configuration, add error states, enforce HTTPS, and deploy the frontend as a static asset while keeping dynamic selection behind a documented API.
