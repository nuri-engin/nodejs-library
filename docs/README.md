# ![Logo](media/nodejs.png)

# Project architecture.

- Review the [Architecture Diagram](architecture/README.md).
- Folder design information of the application.

```
.
+-- build                           '	Executable version of the project.
+-- docs						    '	Project, documents.
+-- public                          '	Project, web content.
+-- reports                         '	Project, coverage, test, screen.
|   +-- coverage                    '	Project, coverage web content.
|   |   +-- index.html              '	Project, coverage report static file
|   +-- document                    '	Project, document web content.
|   |   +-- index.html              '	Project, document report static file
|   +-- tests                       '	Project, test and coverage result.
|   |   +-- cobertura-coverage.xml  '	Project, coverage result.
|   |   +-- junit.xml               '	Project, Unit test result.
|   +-- screen                      '	Project, e2e screens.
+-- src							    '	Project resource files.
|   ?-- api					        '	In-app services.
|   ?-- assets			            '	Design assets.
|   ?-- controllers	                '	The parts that separate the business logic of the application and the user interface.
|   ?-- core					    '	Application core.
|   ?-- models					    '	View objects that separate the Controller From the user interface.
|   ?-- views					    '	The area users view with models.
+-- tests                           '	Project testing.
|   +-- e2e						    '	End-to-end test.
|   +-- unit					    '	Unit test.
|   +-- integration                 '	Integration testing.
+-- .editor.config                  '	Developers will use these code indents and styles in their IDEs.
+-- .env                            '	each env. the file holds or separates the development environment definitions.
+-- docker-compose.yml              '	each .yml file holds or separates runtime definitions.
+-- dockerfile                      '	each docker file prepares the runtime launcher image.

```

# Project development architecture

```
node:alpine
tests:jest
testsResult:jest-unit
coverage:jest
document:jsdoc
pretier:pretier
linter:eslint
stage:lint-stage
version:npm version patch
environment:dotenv
```

## Environment

```
.env
.env.production
.env.development
.env.test
```

## Nodejs Install

Install https://nodejs.org/

```shell
$ npm install
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
```

### Nodejs - Development

Start Linter

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run lint
```

Start Pretier

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run pretier
```

Start Test and Generate test report

xml [ ./reports/tests/junit.xml ]

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run test:development
```

Start Coverage and Generate coverage report

html [ ./reports/coverage ]

xml [ ./reports/test/cobertura-coverage.xml ]

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run coverage
```

Generate Document

html [ ./reports/document ]

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run document
```

Build

binary [ ./build ]

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run build:development
```

Start

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run start:development
```

### Nodejs - Production

Start Linter

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run lint
```

Start Pretier

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run pretier
```

Start Test and Generate test report

xml [ ./reports/tests/junit.xml ]

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run test:production
```

Start Coverage and Generate coverage report

html [ ./reports/coverage ]

xml [ ./reports/test/cobertura-coverage.xml ]

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run coverage
```

Generate Document

html [ ./reports/document ]

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run document
```

Build

binary [ ./build ]

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run build
```

Start

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run start:production
```

### Nodejs - Test

Start Linter

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run lint
```

Start Pretier

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run pretier
```

Start Test and Generate test report

xml [ ./reports/tests/junit.xml ]

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run test:test
```

Start Coverage and Generate coverage report

html [ ./reports/coverage ]

xml [ ./reports/test/cobertura-coverage.xml ]

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run coverage
```

Generate Document

html [ ./reports/document ]

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run document
```

Build

binary [ ./build ]

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run build:test
```

Start

```shell
▀ ╢█████████████░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░╟
$ npm run start:test
```

## Docker Install

```
development : dockerfile.development
production  : dockerfile.production
test        : dockerfile.test
```

### Docker Development

```docker
docker-compose -f "docker-compose-development.yml" up -d --build
```

### Docker Production

```docker
docker-compose -f "docker-compose-production.yml" up -d --build
```

### Docker Test

```docker
docker-compose -f "docker-compose-test.yml" up -d --build
```
