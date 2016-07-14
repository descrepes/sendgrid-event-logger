# ![Logo](./img/logo.png) Sendgrid Event Logger

Small, fast http server to log Sendgrid Event Callback API to Elasticsearch

[![Build Status](https://travis-ci.org/slebetman/sendgrid-event-logger.svg?branch=master)](https://travis-ci.org/slebetman/sendgrid-event-logger)
[![Coverage Status](https://coveralls.io/repos/github/slebetman/sendgrid-event-logger/badge.svg?branch=master)](https://coveralls.io/github/slebetman/sendgrid-event-logger?branch=master)

![Kibana](./img/Kibana-Screen-Shot.png)

*Monitoring sendgrid events on Kibana dashboard*

## Installing

1. Install Elasticsearch. Refer to the docs for details:
https://www.elastic.co/guide/en/elasticsearch/reference/current/_installation.html

2. Upload the index template to elasticsearch:

        curl -XPUT elasticsearch_server:9200/_template/sendgrid_template -T elasticsearch-template.json

3. Edit config.json if necessary.

4. Run the server:

        ./sendgrid-event-logger

## Integrating with Kibana

1. Install Kibana. Refer to the docs for details:

2. Configure a new index pattern.
    - Select "Index contains time-based events" checkbox
	- In the "Index name or pattern" entry type: `mail-*`
	- In the "Time-field name" entry select "timestamp"
	- Press "Create"

## License

Copyright (C) 2016 TrustedCompany.com

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License version 2 as
published bythe Free Software Foundation

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.
