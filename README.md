# SQL Eagle

SQL Eagle is a command-line toolkit for authorized web-application and database security assessments. It helps security professionals identify and validate SQL injection risks, fingerprint database backends, and document findings in controlled testing environments.

> **Authorization required:** Use SQL Eagle only against applications, systems, and databases that you own or have explicit permission to assess. Testing third-party targets without authorization may be illegal.

## What it does

SQL Eagle provides automated support for:

- Detecting potential SQL injection points in HTTP requests.
- Testing boolean-based, error-based, time-based, UNION-based, stacked-query, and out-of-band techniques.
- Identifying supported database management systems.
- Enumerating databases, tables, columns, users, and schemas during an authorized assessment.
- Exporting assessment results and retaining session data for later review.
- Working with URL parameters, POST data, cookies, proxies, HTTP/2, and WebSockets.
- Extending request handling through optional tamper scripts and database-specific plugins.

## Requirements

- Python 3.x is recommended.
- A permitted test target or a local security-testing lab.

The project includes its runtime dependencies and does not require a separate package installation for normal use.

## Getting started

Clone this repository and view the available options:

```bash
git clone https://github.com/lordeagle-tech/sqleagle.git
cd sqleagle
python3 sqlmap.py -h
```

For the complete option reference:

```bash
python3 sqlmap.py -hh
```

A typical assessment command must target an authorized URL. For example, in a local lab:

```bash
python3 sqlmap.py -u "http://127.0.0.1:8000/item?id=1" --batch
```

Do not copy this command to a system you do not control or have permission to test.

## Project layout

- `sqlmap.py` — command-line entry point.
- `sqlmapapi.py` — optional REST API entry point.
- `lib/` — scanning engine, request handling, detection techniques, and output logic.
- `plugins/` — generic and database-specific functionality.
- `data/` — payload definitions, query templates, and supporting data.
- `tamper/` — optional payload transformation modules.
- `tests/` — automated tests.
- `doc/ARCHITECTURE.md` — implementation architecture and contributor guidance.

## Upstream attribution

SQL Eagle is a rebranded distribution based on the open-source [sqlmap](https://github.com/sqlmapproject/sqlmap) project. The upstream project and its contributors retain credit for the original code and technical work. This repository keeps the applicable license and attribution files.

## License

This project is distributed under the GNU General Public License, version 2. See [`LICENSE`](LICENSE) and [`COPYING`](COPYING) for the applicable terms.

## Disclaimer

The maintainers provide this software for legitimate security testing and research. Users are responsible for obtaining authorization, complying with applicable laws, and protecting any data encountered during an assessment.
