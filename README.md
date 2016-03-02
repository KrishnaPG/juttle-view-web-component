# Juttle View Web Component

*Note: This is a Proof of Concept.*

Embed [juttle](https://github.com/juttle/juttle) powered [visualization](https://github.com/juttle/juttle-viz) directly in your HTML using a [Web Component](https://developer.mozilla.org/en-US/docs/Web/Web_Components).

## Install
```bash
$ git clone https://github.com/juttle/juttle-view-web-component
$ npm install
```

Install and start [juttle-service](https://github.com/juttle/juttle-service) on its default port (the component assumes juttle-service is running at `http://localhost:2000`).

## Example Usage


```html
<html>
  <head>
    <script src="node_modules/webcomponents.js/webcomponents-lite.min.js"></script>
    <link rel="import" href="juttle-view-element.html">
    <style type="text/css">
      body { background-color: black; }
    </style>
  </head>
  <body>
    <juttle-view juttle="emit -limit 10 -from :10 seconds ago: | put v = count() * 2" type="timechart" options="{ title: 'a timechart'}"></juttle-view>
    <juttle-view juttle="emit -limit 2 | put v = count()"></juttle-view>
  </body>
</html>

```

## Supported Attributes
- **juttle**: The juttle to run (without the sink).
- **type** (default: table): The type of view to output.
- **options**: Options to pass to the view.
