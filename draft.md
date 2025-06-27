`vimana`
![image](https://github.com/user-attachments/assets/7b84db0a-0cc2-4a17-a10b-fac8b93d3927)


list plugins
```
vimana list --plugins
```
![image](https://github.com/user-attachments/assets/57fae534-d5d8-4d42-b3e4-e0a06ef91a7b)

framewalk info
```
vimana info --plugin framewalk
```
![image](https://github.com/user-attachments/assets/6fa50c8e-e84c-4e9e-aa11-40bc7d08158d)


Discovery via --target-url 
```
vimana run framewalk --target http://127.0.0.1:5000/
```
![image](https://github.com/user-attachments/assets/b091b81a-289d-494b-9b25-5c32a28e273c)
![image](https://github.com/user-attachments/assets/c9f86131-4b95-40e2-af9e-61b8c3354c53)
![image](https://github.com/user-attachments/assets/33eef820-bedc-45af-be75-0c177f3955b0)

Multi target with summary-only option
```
vimana run framewalk --file siddhis/framewalk/targets.txt --summary-only
```
![image](https://github.com/user-attachments/assets/945c6386-233d-4e21-8b70-bd48617215de)
![image](https://github.com/user-attachments/assets/1b0f8198-67ca-4007-9119-542ed4cd3e93)

Multi target without --summary-only will show the detailed output for each of the targets as can be seen in the full output below
<details>
<summary>Show full DMT Output</summary>

```python
(vfe0.8) ➟ vimana run framewalk --file siddhis/framewalk/targets.txt 

[Target 1/3] Scanning: http://localhost:8003
╭──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│                                                                                                                                                                                                                  │
│                         ●                                                                                                                                                                                        │
│                                            ╭──────╨─────────╮                                                                                                                                                    │
│                                            │            ◎   │                                                                                                                                                    │
│                                            │  ╭──────╮      │                                                                                                                                                    │
│                                            │  │Bottle░      │                                                                                                                                                    │
│       ╔═══════════════════════╗            │  ╰──┬───╯      │                                                                                                                                                    │
│       ║ ╭────╮  FRAMEWALK  ★  ║╮           │     │          │                                                                                                                                                    │
│       ║ │ ◎─│───────────────────◎          │  ╭──┴───╮      │                                                                                                                                                    │
│       ║ ╰────╯                ║╯           │  │Sanic ├──────┤                                                                                                                                                    │
│ ╭─────╨─────────╮             ║            │  ╰──────╯      │                                                                                                                                                    │
│ │  ╭──────╮     │             ║            │             ╭──┴───╮                                                                                                                                                │
│ │  │Django├──┬──╯       ╭─────╯            └─────╭───────┤Web2py│                                                                                                                                                │
│ │  ╰──────╯  │     ╭────┴╮                       │       ╰──────╯                                                                                                                                                │
│ ╰─────┬──────╯     │Flask│───●──●──●─────────────╯                                                                                                                                                               │
│       │  ●         ╰──╭──╯                                                                                                                                                                                       │
│    ╭──┴────╮   ╭─────╯│       ╭──●                                                                                                                                                                               │
│    │FastAPI ───╯      ╰───────│                                                                                                                                                                                  │
│    ╰───────╯                  ╰──● Tornado                                                                                                                                                                       │
│                                                                                                                                                                                                                  │
│                                                                                                                                                                                                                  │
╰──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
  Running engines   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 5/5 0:00:00
  Running detectors ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 5/5 0:00:00


─────────────────────────────────────────────────────────────────────────────────────────────────── Scan Results ───────────────────────────────────────────────────────────────────────────────────────────────────

Target: http://localhost:8003
Scan time: 0.16 seconds
IP: 127.0.0.1
Server: uvicorn

Security Headers:
╭────────────────────────┬─────────╮
│ Header                 │ Status  │
├────────────────────────┼─────────┤
│ HSTS                   │ Missing │
│ CSP                    │ Missing │
│ X-Content-Type-Options │ Missing │
│ X-Frame-Options        │ Missing │
│ X-XSS-Protection       │ Missing │
│ Referrer-Policy        │ Missing │
│ Permissions-Policy     │ Missing │
│ COEP                   │ Missing │
│ COOP                   │ Missing │
│ CORP                   │ Missing │
╰────────────────────────┴─────────╯

Detected Frameworks:
╭───────────┬─────────────────────────────┬─────────┬───────────────────────────────────────────────────────────────────╮
│ Framework │ Confidence                  │ Version │ Components                                                        │
├───────────┼─────────────────────────────┼─────────┼───────────────────────────────────────────────────────────────────┤
│ FastAPI   │ 100% [████████████████████] │ 0.89+   │ Swagger UI, FastAPI OAuth2, OpenAPI, Health Check, Uvicorn, ReDoc │
│ Django    │ 16% [███░░░░░░░░░░░░░░░░░]  │ Unknown │ Django REST Framework                                             │
│ Flask     │ 4% [░░░░░░░░░░░░░░░░░░░░]   │ Unknown │ None detected                                                     │
╰───────────┴─────────────────────────────┴─────────┴───────────────────────────────────────────────────────────────────╯

Detection Evidence:
Evidence by Framework
├── FastAPI
│   ├── Server
│   │   ├── ASGI server detected: uvicorn
│   │   └── Uvicorn ASGI server detected
│   ├── Endpoint
│   │   ├── /docs returns 200 OK
│   │   ├── /redoc returns 200 OK
│   │   └── /openapi.json returns 200 OK
│   ├── Documentation
│   │   ├── Swagger UI detected at /docs
│   │   └── ReDoc detected at /redoc
│   ├── Component
│   │   ├── Swagger UI (Documentation at /docs)
│   │   ├── ReDoc (Documentation at /redoc)
│   │   ├── OpenAPI (Schema version: 3.1.0)
│   │   ├── Uvicorn (ASGI server: uvicorn)
│   │   ├── FastAPI OAuth2 (OAuth2 authentication)
│   │   └── Health Check (Health check endpoint)
│   ├── OpenAPI
│   │   └── OpenAPI schema found at /openapi.json
│   ├── Header
│   │   └── Server header contains uvicorn: uvicorn
│   ├── Dependency
│   │   ├── FastAPI OAuth2 detected at /docs/oauth2-redirect
│   │   └── Health Check detected at /health
│   ├── Schema
│   │   ├── OpenAPI schema at /openapi.json
│   │   └── FastAPI schema indicators (29 patterns)
│   └── Content
│       └── FastAPI reference in HTML
├── Django
│   ├── Server
│   │   └── ASGI server detected: uvicorn
│   ├── API
│   │   ├── ReDoc API docs at /redoc/
│   │   └── OpenAPI schema at /redoc/
│   └── Component
│       └── Django REST Framework (API component at /redoc/)
└── Flask
    └── Path
        └── Common Flask path exists: /docs/

Recommendations:
• Primary target appears to be: FastAPI
• High confidence detection - proceed with framework-specific testing

────────────────────────────────────────────────────────────────────────────────


[Target 2/3] Scanning: http://localhost:8000
  Running engines   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 5/5 0:00:04
  Running detectors ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 5/5 0:00:12


─────────────────────────────────────────────────────────────────────────────────────────────────── Scan Results ───────────────────────────────────────────────────────────────────────────────────────────────────

Target: http://localhost:8000
Scan time: 17.38 seconds
IP: 127.0.0.1

Security Headers:
╭────────────────────────┬─────────╮
│ Header                 │ Status  │
├────────────────────────┼─────────┤
│ X-Frame-Options        │ Present │
│ HSTS                   │ Missing │
│ CSP                    │ Missing │
│ X-Content-Type-Options │ Missing │
│ X-XSS-Protection       │ Missing │
│ Referrer-Policy        │ Missing │
│ Permissions-Policy     │ Missing │
│ COEP                   │ Missing │
│ COOP                   │ Missing │
│ CORP                   │ Missing │
╰────────────────────────┴─────────╯

Detected Frameworks:
╭───────────┬─────────────────────────────┬─────────┬───────────────╮
│ Framework │ Confidence                  │ Version │ Components    │
├───────────┼─────────────────────────────┼─────────┼───────────────┤
│ Django    │ 100% [████████████████████] │ All     │ Django Admin  │
│ Flask     │ 3% [░░░░░░░░░░░░░░░░░░░░]   │ Unknown │ None detected │
│ FastAPI   │ 3% [░░░░░░░░░░░░░░░░░░░░]   │ Unknown │ None detected │
│ Pyramid   │ 3% [░░░░░░░░░░░░░░░░░░░░]   │ Unknown │ None detected │
│ Bottle    │ 3% [░░░░░░░░░░░░░░░░░░░░]   │ Unknown │ None detected │
╰───────────┴─────────────────────────────┴─────────┴───────────────╯

Detection Evidence:
Evidence by Framework
├── Django
│   ├── Header
│   │   ├── Header contains Python reference: server
│   │   └── Django-like Vary header with Cookie
│   ├── Security Header
│   │   └── Django default X-Frame-Options: SAMEORIGIN
│   ├── Server
│   │   └── Python version leak: 3.6.9
│   ├── Endpoint
│   │   ├── /admin/ returns 200 OK
│   │   └── /admin/login/ returns 200 OK
│   ├── Content
│   │   ├── CSRF middleware token found in HTML
│   │   ├── Django reference in HTML
│   │   ├── Django admin static path found
│   │   ├── Django admin interface detected
│   │   ├── Django admin login page
│   │   ├── Django admin login next parameter
│   │   └── Django admin login CSRF protection
│   ├── Component
│   │   └── Django Admin (Admin interface detected)
│   ├── JavaScript
│   │   └── Django jQuery namespace
│   └── Security
│       └── Django default X-Frame-Options: SAMEORIGIN
├── Flask
│   ├── Header
│   │   └── Header contains Python reference: server
│   └── Server
│       └── Python version leak: 3.6.9
├── FastAPI
│   ├── Header
│   │   └── Header contains Python reference: server
│   └── Server
│       └── Python version leak: 3.6.9
├── Pyramid
│   ├── Header
│   │   └── Header contains Python reference: server
│   └── Server
│       └── Python version leak: 3.6.9
└── Bottle
    ├── Header
    │   └── Header contains Python reference: server
    └── Server
        └── Python version leak: 3.6.9

Recommendations:
• Primary target appears to be: Django
• High confidence detection - proceed with framework-specific testing
• Try these tools: djunch, dmt, jungle

────────────────────────────────────────────────────────────────────────────────


[Target 3/3] Scanning: http://127.0.0.1:5000/
  Running engines   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 5/5 0:00:00
  Running detectors ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 5/5 0:00:00


─────────────────────────────────────────────────────────────────────────────────────────────────── Scan Results ───────────────────────────────────────────────────────────────────────────────────────────────────

Target: http://127.0.0.1:5000/
Scan time: 0.20 seconds
IP: 127.0.0.1

Security Headers:
╭────────────────────────┬─────────╮
│ Header                 │ Status  │
├────────────────────────┼─────────┤
│ HSTS                   │ Missing │
│ CSP                    │ Missing │
│ X-Content-Type-Options │ Missing │
│ X-Frame-Options        │ Missing │
│ X-XSS-Protection       │ Missing │
│ Referrer-Policy        │ Missing │
│ Permissions-Policy     │ Missing │
│ COEP                   │ Missing │
│ COOP                   │ Missing │
│ CORP                   │ Missing │
╰────────────────────────┴─────────╯

Detected Frameworks:
╭───────────┬────────────────────────────┬────────────────┬───────────────────╮
│ Framework │ Confidence                 │ Version        │ Components        │
├───────────┼────────────────────────────┼────────────────┼───────────────────┤
│ Flask     │ 43% [████████░░░░░░░░░░░░] │ Werkzeug 2.0.3 │ Werkzeug Debugger │
│ Django    │ 3% [░░░░░░░░░░░░░░░░░░░░]  │ Unknown        │ None detected     │
│ FastAPI   │ 3% [░░░░░░░░░░░░░░░░░░░░]  │ Unknown        │ None detected     │
│ Pyramid   │ 3% [░░░░░░░░░░░░░░░░░░░░]  │ Unknown        │ None detected     │
│ Bottle    │ 3% [░░░░░░░░░░░░░░░░░░░░]  │ Unknown        │ None detected     │
╰───────────┴────────────────────────────┴────────────────┴───────────────────╯

Detection Evidence:
Evidence by Framework
├── Flask
│   ├── Header
│   │   ├── Header contains Flask/Werkzeug reference: server
│   │   ├── Header contains Python reference: server
│   │   └── Server header contains Werkzeug: Werkzeug/2.0.3 Python/3.6.9
│   ├── Server
│   │   └── Python version leak: 3.6.9
│   ├── Debug
│   │   ├── Werkzeug debugger console found at /console
│   │   └── Werkzeug 'DON'T PANIC' message found
│   └── Component
│       └── Werkzeug Debugger (Interactive console found)
├── Django
│   ├── Header
│   │   └── Header contains Python reference: server
│   └── Server
│       └── Python version leak: 3.6.9
├── FastAPI
│   ├── Header
│   │   └── Header contains Python reference: server
│   └── Server
│       └── Python version leak: 3.6.9
├── Pyramid
│   ├── Header
│   │   └── Header contains Python reference: server
│   └── Server
│       └── Python version leak: 3.6.9
└── Bottle
    ├── Header
    │   └── Header contains Python reference: server
    └── Server
        └── Python version leak: 3.6.9

Recommendations:
• Primary target appears to be: Flask
• Medium/low confidence detection - use manual verification techniques
• Consider deeper analysis with more invasive techniques

────────────────────────────────────────────────────────────────────────────────



────────────────────────────────────────────────────────────────────────────────────────────── Aggregate Scan Results ──────────────────────────────────────────────────────────────────────────────────────────────

Scanned Targets: 3
Total Scan Time: 17.79 seconds
Timestamp: 2025-06-23 10:53:07

Framework Distribution:
╭───────────┬───────┬────────────┬──────────────────────╮
│ Framework │ Count │ Percentage │ Distribution         │
├───────────┼───────┼────────────┼──────────────────────┤
│ FastAPI   │ 3     │ 100.0%     │ ████████████████████ │
│ Django    │ 3     │ 100.0%     │ ████████████████████ │
│ Flask     │ 3     │ 100.0%     │ ████████████████████ │
│ Pyramid   │ 2     │ 66.7%      │ █████████████░░░░░░░ │
│ Bottle    │ 2     │ 66.7%      │ █████████████░░░░░░░ │
╰───────────┴───────┴────────────┴──────────────────────╯

Target Details:
╭────────────────────────┬───────────────┬─────────────────────────────┬───────────┬────────────┬────────────╮
│ Target URL             │ Top Framework │ Confidence                  │ Scan Time │ Frameworks │ Components │
├────────────────────────┼───────────────┼─────────────────────────────┼───────────┼────────────┼────────────┤
│ http://localhost:8003  │ FastAPI       │ 100% [████████████████████] │ 0.16s     │ 3          │ 7          │
│ http://localhost:8000  │ Django        │ 100% [████████████████████] │ 17.38s    │ 5          │ 1          │
│ http://127.0.0.1:5000/ │ Flask         │ 43% [████████░░░░░░░░░░░░]  │ 0.20s     │ 5          │ 1          │
╰────────────────────────┴───────────────┴─────────────────────────────┴───────────┴────────────┴────────────╯

Recommendations:
• Most common framework detected: FastAPI
• Diverse framework usage detected - consider targeting specific framework families

```
</details>

#### Looking for a specific framework in a Multi Target scope

Let say you need to run a multi target scan with hundreds of targets instead of just three as we've seen, and in addition you're interested in finding out which of those targets are running FastAPI, so you can skip other tests, this is how you do this with `--frameworks` filter:
```Python
vimana run framewalk --file siddhis/framewalk/targets.txt  --frameworks FastAPI
```
![image](https://github.com/user-attachments/assets/bd4b620d-5c61-4e23-8796-7ba4853a515f)
![image](https://github.com/user-attachments/assets/7db6ad3a-87db-4967-9411-2649249c0b38)

In this mode filtering by framework we'll see detailed detection information just for the target frameworks, if any, in all other
steps with targets running diferent frameworks we'll see just this message "No frameworks detected with confidence":
![image](https://github.com/user-attachments/assets/0e62260e-db33-472c-b3de-4e14d1a6b616)


### JSON Output
```Json
{
  "target": "http://127.0.0.1:5000/",
  "scan_time": 0.1682591438293457,
  "timestamp": "2025-06-23 11:10:25",
  "ip_info": {
    "hostname": "127.0.0.1",
    "ip": "127.0.0.1"
  },
  "server_info": {},
  "security": {
    "headers": {
      "present": [],
      "missing": [
        "HSTS",
        "CSP",
        "X-Content-Type-Options",
        "X-Frame-Options",
        "X-XSS-Protection",
        "Referrer-Policy",
        "Permissions-Policy",
        "COEP",
        "COOP",
        "CORP"
      ]
    }
  },
  "frameworks": [
    {
      "name": "Flask",
      "confidence": 43,
      "version": "Werkzeug 2.0.3",
      "components": [
        "Werkzeug Debugger"
      ],
      "vulnerabilities": [],
      "metadata": {
        "description": "Lightweight WSGI web application framework",
        "website": "https://flask.palletsprojects.com/"
      },
      "evidence": {
        "Header": [
          "Header contains Flask/Werkzeug reference: server",
          "Header contains Python reference: server",
          "Server header contains Werkzeug: Werkzeug/2.0.3 Python/3.6.9"
        ],
        "Server": [
          "Python version leak: 3.6.9"
        ],
        "Debug": [
          "Werkzeug debugger console found at /console",
          "Werkzeug 'DON'T PANIC' message found"
        ],
        "Component": [
          "Werkzeug Debugger (Interactive console found)"
        ]
      }
    },
    {
      "name": "Django",
      "confidence": 3,
      "version": "Unknown",
      "components": [],
      "vulnerabilities": [],
      "metadata": {
        "description": "High-level Python web framework",
        "website": "https://www.djangoproject.com/"
      },
      "evidence": {
        "Header": [
          "Header contains Python reference: server"
        ],
        "Server": [
          "Python version leak: 3.6.9"
        ]
      }
    },
    {
      "name": "FastAPI",
      "confidence": 3,
      "version": "Unknown",
      "components": [],
      "vulnerabilities": [],
      "metadata": {
        "description": "Modern, fast, web framework for building APIs",
        "website": "https://fastapi.tiangolo.com/"
      },
      "evidence": {
        "Header": [
          "Header contains Python reference: server"
        ],
        "Server": [
          "Python version leak: 3.6.9"
        ]
      }
    },
    {
      "name": "Pyramid",
      "confidence": 3,
      "version": "Unknown",
      "components": [],
      "vulnerabilities": [],
      "metadata": {
        "description": "Small, fast, down-to-earth Python web framework",
        "website": "https://trypyramid.com/"
      },
      "evidence": {
        "Header": [
          "Header contains Python reference: server"
        ],
        "Server": [
          "Python version leak: 3.6.9"
        ]
      }
    },
    {
      "name": "Bottle",
      "confidence": 3,
      "version": "Unknown",
      "components": [],
      "vulnerabilities": [],
      "metadata": {
        "description": "Fast and simple micro-framework for Python web applications",
        "website": "https://bottlepy.org/"
      },
      "evidence": {
        "Header": [
          "Header contains Python reference: server"
        ],
        "Server": [
          "Python version leak: 3.6.9"
        ]
      }
    }
  ]
}

```
