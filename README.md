# Universal Widget

This project serves a [single static webpage](https://gsurrel.github.io/no-host-static-page/) that has several goals:

1. Explain how the project works.
1. Provide an easy way to create a serverless static page (or widget).
1. Render a Base 64 encoded page.

## Is it really serverless?

No, it's not absolutely serverless: [the page that does all the work](https://gsurrel.github.io/no-host-static-page/) needs to be hosted somewhere. However, once that page is online, you can use it to create any kind of page, without the requirement to host it anywhere: all the page source is stored in the fragment part of the URL (after the `#` sign).


## Is it secure?

Yes and no. Yes, in the sense the server will never know what page is generated from the encoded content: the fragment is never sent online. No, in the sense it can be used to display anything, including malicious forms to send data elsewhere.


## Can I get a demo?

Let's have several examples. The first one will be [a very simple document with the content `<h1>Hello!</h1>`](https://gsurrel.github.io/no-host-static-page/#PGgxPkhlbGxvITwvaDE+). Notice that the `<h1>Hello!</h1>` content has been encoded to `PGgxPkhlbGxvITwvaDE+` in the address bar, after the `#`.


The second demo creates a complete page, with fully working Javascript (if that matters to you): [second example, more complex](https://gsurrel.github.io/no-host-static-page/#PCFET0NUWVBFIGh0bWw+PGh0bWw+PGhlYWQ+ICAgIDxtZXRhIGNoYXJzZXQ9IlVURi04Ij4gICAgPG1ldGEgaHR0cC1lcXVpdj0iWC1VQS1Db21wYXRpYmxlIiBjb250ZW50PSJJRT1lZGdlIj4gICAgPG1ldGEgbmFtZT0idmlld3BvcnQiIGNvbnRlbnQ9IndpZHRoPWRldmljZS13aWR0aCwgaW5pdGlhbC1zY2FsZT0xLjAiPiAgICA8c2NyaXB0IHNyYz0iaHR0cHM6Ly9jZG4uanNkZWxpdnIubmV0L25wbS92ZWdhQDUiPjwvc2NyaXB0PiAgICA8c2NyaXB0IHNyYz0iaHR0cHM6Ly9jZG4uanNkZWxpdnIubmV0L25wbS92ZWdhLWxpdGVANSI+PC9zY3JpcHQ+ICAgIDxzY3JpcHQgc3JjPSJodHRwczovL2Nkbi5qc2RlbGl2ci5uZXQvbnBtL3ZlZ2EtZW1iZWRANiI+PC9zY3JpcHQ+PC9oZWFkPjxib2R5PiAgICA8aDE+U3RhY2tlZCBCYXIgQ2hhcnQ8L2gxPiAgICA8cD5UaGlzIHdlYnBhZ2Ugd2l0aCBhIHN0YWNrZWQgYmFyIGNoYXJ0IGlzIGdlbmVyYXRlZCBjb21wbGV0ZWx5IGluIHlvdXIgYnJvd3Nlci4gSXQgbGl2ZXMgZXhjbHVzaXZlbHkgaW4gdGhlICAgICAgICBhZGRyZXNzIGJhciBvZiB5b3VyIGJyb3dzZXIsIGFuZCBpc24ndCBzdG9yZWQgYW55d2hlcmUgZWxzZS48L3A+ICAgIDxkaXYgaWQ9InZpZXciPjwvZGl2PiAgICA8c2NyaXB0PiAgICAgICAgdmFyIHNwZWMgPSB7ICAgICAgICAgICAgIiRzY2hlbWEiOiAiaHR0cHM6Ly92ZWdhLmdpdGh1Yi5pby9zY2hlbWEvdmVnYS1saXRlL3Y1Lmpzb24iLCAgICAgICAgICAgICJkYXRhIjogeyAidXJsIjogImh0dHBzOi8vdmVnYS5naXRodWIuaW8vdmVnYS1saXRlL2V4YW1wbGVzL2RhdGEvc2VhdHRsZS13ZWF0aGVyLmNzdiIgfSwgICAgICAgICAgICAibWFyayI6ICJiYXIiLCAgICAgICAgICAgICJlbmNvZGluZyI6IHsgICAgICAgICAgICAgICAgIngiOiB7ICAgICAgICAgICAgICAgICAgICAidGltZVVuaXQiOiAibW9udGgiLCAgICAgICAgICAgICAgICAgICAgImZpZWxkIjogImRhdGUiLCAgICAgICAgICAgICAgICAgICAgInR5cGUiOiAib3JkaW5hbCIsICAgICAgICAgICAgICAgICAgICAidGl0bGUiOiAiTW9udGggb2YgdGhlIHllYXIiICAgICAgICAgICAgICAgIH0sICAgICAgICAgICAgICAgICJ5IjogeyAgICAgICAgICAgICAgICAgICAgImFnZ3JlZ2F0ZSI6ICJjb3VudCIsICAgICAgICAgICAgICAgICAgICAidHlwZSI6ICJxdWFudGl0YXRpdmUiICAgICAgICAgICAgICAgIH0sICAgICAgICAgICAgICAgICJjb2xvciI6IHsgICAgICAgICAgICAgICAgICAgICJmaWVsZCI6ICJ3ZWF0aGVyIiwgICAgICAgICAgICAgICAgICAgICJ0eXBlIjogIm5vbWluYWwiLCAgICAgICAgICAgICAgICAgICAgInNjYWxlIjogeyAgICAgICAgICAgICAgICAgICAgICAgICJkb21haW4iOiBbInN1biIsICJmb2ciLCAiZHJpenpsZSIsICJyYWluIiwgInNub3ciXSwgICAgICAgICAgICAgICAgICAgICAgICAicmFuZ2UiOiBbIiNlN2JhNTIiLCAiI2M3YzdjNyIsICIjYWVjN2U4IiwgIiMxZjc3YjQiLCAiIzk0NjdiZCJdICAgICAgICAgICAgICAgICAgICB9LCAgICAgICAgICAgICAgICAgICAgInRpdGxlIjogIldlYXRoZXIgdHlwZSIgICAgICAgICAgICAgICAgfSAgICAgICAgICAgIH0gICAgICAgIH07ICAgICAgICB2ZWdhRW1iZWQoICAgICAgICAgICAgJyN2aWV3JywgICAgICAgICAgICBzcGVjICAgICAgICApOyAgICA8L3NjcmlwdD48L2JvZHk+PC9odG1sPg==) with a [Vega-Lite chart](https://vega.github.io/vega-lite/) that is hosted nowhere.

If you are interested, here is the decoded source:

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
    <script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
    <script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
</head>

<body>
    <h1>Stacked Bar Chart</h1>
    <p>This webpage with a stacked bar chart is generated completely in your browser. It lives exclusively in the
        address bar of your browser, and isn't stored anywhere else.</p>
    <div id="view"></div>
    <script>
        var spec = {
            "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
            "data": { "url": "https://vega.github.io/vega-lite/examples/data/seattle-weather.csv" },
            "mark": "bar",
            "encoding": {
                "x": {
                    "timeUnit": "month",
                    "field": "date",
                    "type": "ordinal",
                    "title": "Month of the year"
                },
                "y": {
                    "aggregate": "count",
                    "type": "quantitative"
                },
                "color": {
                    "field": "weather",
                    "type": "nominal",
                    "scale": {
                        "domain": ["sun", "fog", "drizzle", "rain", "snow"],
                        "range": ["#e7ba52", "#c7c7c7", "#aec7e8", "#1f77b4", "#9467bd"]
                    },
                    "title": "Weather type"
                }
            }
        };

        vegaEmbed(
            '#view',
            spec
        );
    </script>
</body>

</html>
```

It can be also used in `<iframe>` elements, for example in Atlassian's Confluence pages.
