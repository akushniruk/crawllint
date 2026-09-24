# CrawlLint

> Lint the entire website, not just its code.

CrawlLint is an open-source website crawler and technical SEO auditing tool intended to be written in Go. Its long-term goal is an extensible rule and plugin system for SEO, accessibility, performance, security, and general website-quality checks.

> **Work in progress:** CrawlLint is currently at the repository bootstrap stage. There is no crawler, CLI, Go module, or rule engine yet.

Contributions are welcome early. See [Ideas for first contributions](#ideas-for-first-contributions) for useful starting points.

## Project status

CrawlLint is pre-alpha and not usable yet. The repository currently contains only the Apache License 2.0. No executable code, releases, packages, or supported installation method exist.

The sections below separate current repository facts from planned direction.

## Why CrawlLint exists

Website-quality checks are often spread across unrelated tools and one-off scripts. CrawlLint aims to provide one inspectable, automation-friendly crawler that can apply consistent checks across an entire site.

The project is intended to help developers and contributors:

- find issues across pages rather than inspect one URL at a time;
- express checks as focused, testable rules;
- add new categories of checks without rewriting the crawler;
- use the same audits locally and in automated workflows.

## Implemented features

No runtime features are implemented yet.

Current repository contents:

- Apache License 2.0;
- initial project definition in this README.

## Planned features

The following are goals, not available functionality:

- crawl a website from a starting URL;
- discover and inspect internal pages;
- apply configurable crawl limits and rate limits;
- respect `robots.txt`;
- report HTTP and metadata issues;
- support SEO, accessibility, performance, security, and quality rules;
- provide an extensible rule and plugin model;
- produce useful terminal output and machine-readable reports;
- support automated testing and CI usage.

Scope and interfaces will be refined as the first implementation is designed.

## Installation

CrawlLint cannot be installed yet. There is no Go module, binary, package, or release.

To inspect the current repository:

```sh
git clone https://github.com/akushniruk/crawllint.git
cd crawllint
```

<!-- TODO: Add supported installation commands after the first runnable release exists. -->
<!-- TODO: Document the required Go version after go.mod is added. -->

## CLI usage

There is no CLI implementation, so there are no valid usage examples yet.

<!-- TODO: Replace this section with examples copied from the implemented CLI and verified against its help output. -->

## High-level architecture

No application architecture is implemented. A likely direction is to keep these responsibilities separate:

1. URL discovery and crawl scheduling.
2. HTTP fetching and response handling.
3. Document parsing and normalized page data.
4. Independent audit rules.
5. Result aggregation and reporting.
6. Configuration and future plugin loading.

This is a proposed boundary, not a description of existing packages. Concrete package structure and extension interfaces should be decided through implementation and review.

## Development setup

Current setup requires only Git because there is no source code to build.

```sh
git clone https://github.com/akushniruk/crawllint.git
cd crawllint
git status
```

A Go toolchain will be required once the module is created.

<!-- TODO: Add exact build, formatting, linting, and local-run commands when they exist. -->

## Tests

No test suite or test command exists yet.

<!-- TODO: Add the verified test command after the Go module and first tests are committed. -->

## Contributing

CrawlLint is early enough for contributors to help shape its foundations.

Before starting substantial work:

1. Open an issue describing the problem and proposed scope.
2. Keep the first change small and focused.
3. Add tests with new behavior once the test structure exists.
4. Update documentation when behavior or commands change.
5. Submit a pull request that explains the change and its validation.

Avoid documenting planned behavior as implemented. Examples in this README should be runnable against the repository version that contains them.

<!-- TODO: Add a CONTRIBUTING.md with code style, review, and release policies. -->

## Ideas for first contributions

- Propose the minimal CLI contract and configuration format.
- Initialize the Go module and define the supported Go version.
- Design a small crawler interface with cancellation and crawl limits.
- Add URL normalization and same-site boundary tests.
- Define the first rule interface and result model.
- Implement a basic HTTP status check with tests.
- Add formatting, linting, and test checks for CI.
- Document responsible crawling defaults and failure behavior.

Discuss interface-heavy changes in an issue before implementation so early contributions converge on a coherent core.

## Responsible use

Only crawl websites you are authorized to access. Respect `robots.txt`, website terms, server capacity, and applicable law. Use reasonable concurrency and rate limits. CrawlLint should not be used to disrupt services or bypass access controls.

## License

CrawlLint is licensed under the [Apache License 2.0](LICENSE).
