
# HTML

```masteryls
{"id":"b9e2c3d4-e5f6-7890-1234-567890123460", "title":"AI Web Page (Prompt + Starter HTML)", "type":"ai-web-page", "height":420, "gradingCriteria":"Create a responsive page with semantic HTML, accessible labels, and a clear call-to-action. Score based on structure, accessibility, and prompt alignment."}
Build a landing page for a student coding club.
Use the prompt box to generate a first version, then edit and submit.

~~~html
<!doctype html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Coding Club</title>
    <style>
      body { font-family: sans-serif; margin: 0; padding: 24px; }
      main { max-width: 720px; margin: 0 auto; }
      .cta { display: inline-block; padding: 10px 14px; background: #0b60d0; color: #fff; text-decoration: none; border-radius: 8px; }
    </style>
  </head>
  <body>
    <main>
      <h1>Join Cow Coding Club</h1>
      <p>Build projects, prepare for hackathons, and level up your skills.</p>
      <a class="cta" href="#join">Join now</a>
    </main>
  </body>
</html>
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