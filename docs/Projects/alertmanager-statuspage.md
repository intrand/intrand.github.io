# alertmanager-statuspage

`alertmanager-statuspage` takes `alertmanager` alerts and turns them into statuspage.io updates.

## Design

`alertmanager-statuspage` utilizes your existing `prometheus` and `alertmanager` instances to generate updates by matching unique labels you inject to your metrics. This is done via the `prometheus` configuration YAML file with just a few options. For example, assuming you use `blackbox-exporter` to scrape `http_2xx` from a web service, you can attach the relevant statuspage.io "page" and "component" IDs to every metric scraped.

## Status

Abandoned. I don't have time to maintain this anymore and I stopped hosting things myself.
