
# HTML


```masteryls
{"id":"aea2c9b9-bf13-4019-a5d2-363da735f3e0", "title":"Web page", "type":"web-page", "height":250}
  <body style="margin:0;display:grid;place-items:center;min-height:100vh;background:radial-gradient(circle at 20% 20%,#22d3ee,#0f172a);color:#ecfeff;font-family:ui-monospace,monospace;">
    <h1 style="font-size:clamp(1.4rem,4vw,2.4rem);letter-spacing:.06em;">Hello, curious learner.</h1>
  </body>
```


```masteryls
{"id":"b0c3c187-8e65-4d4f-9f60-b2aae1941d04", "title":"Web page development", "type":"ai-web-page", "height":500 }
Interactively create an HTML page from your prompt.

~~~html
  <body style="margin:0;display:grid;place-items:center;min-height:100vh;background:radial-gradient(circle at 20% 20%,#22d3aa,#004949);color:#ecfeff;font-family:ui-monospace,monospace;">
    <h1 style="font-size:clamp(1.4rem,4vw,2.4rem);letter-spacing:.06em;">Hello, curious learner.</h1>
  </body>
~~~
```



```masteryls
{"id":"a9b2c3d4-e5f6-7890-1234-567890123460", "title":"Animation usage", "type":"ai-web-page", "height":420}
Demonstrate the use of CSS animation. The web page should include at least one animation that repeats.
```


```masteryls
{"id":"a9d2c3d4-e5f6-7890-1234-567890123460", "title":"AI web page", "type":"web-page", "file":"demo/pickle.html", "height":420}
```

```masteryls
{"id":"a9c2c3d4-e5f6-7890-1234-567890123460", "title":"Basic React Demo", "type":"web-page", "height":420}
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>React CDN Demo</title>

  <!-- React + ReactDOM via CDN -->
  <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
  <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>

  <!-- Babel for JSX support in browser (dev only) -->
  <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .app {
      background: white;
      padding: 20px 30px;
      border-radius: 10px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
      text-align: center;
    }

    button {
      margin-top: 10px;
      padding: 8px 16px;
      font-size: 16px;
      border: none;
      border-radius: 6px;
      background: #007bff;
      color: white;
      cursor: pointer;
    }

    button:hover {
      background: #0056b3;
    }
  </style>
</head>
<body>
  <div id="root"></div>

  <script type="text/babel">
    function App() {
      const [count, setCount] = React.useState(0);

      return (
        <div className="app">
          <h1>React Demo</h1>
          <p>Count: {count}</p>
          <button onClick={() => setCount(count + 1)}>
            Increment
          </button>
        </div>
      );
    }

    const root = ReactDOM.createRoot(document.getElementById('root'));
    root.render(<App />);
  </script>
</body>
</html>
```