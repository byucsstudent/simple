
# HTML

```html
  <body style="margin:0;display:grid;place-items:center;min-height:100vh;background:radial-gradient(circle at 20% 20%,#d3aa,#004049);color:#ecfeff;font-family:ui-monospace,monospace;">
    <h1 style="font-size:clamp(1.4rem,4vw,2.4rem);letter-spacing:.06em;">React router</h1>
  </body>
```


```masteryls
{"id":"05db5593-00b4-4dbd-ac28-b0ac04205e27", "title":"Dom Reactivity", "type":"ai-web-page", "gradingCriteria":"Demonstrates direct manipulation of the DOM", "height":500 }
Demonstrate directly manipulating the DOM to represent state.

~~~html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>DOM Reactivity Demo</title>
    <style>
      :root {
        --primary: #fbdc9e;
        --secondary: #282c34;
        --text: #333;
        --bg: #f4f7f6;
        --card-bg: #ffffff;
        --border: #ddd;
        --success: #4caf50;
      }

      * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
      }

      body {
        font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
        line-height: 1.6;
        color: var(--text);
        background-color: var(--bg);
        padding: 20px;
      }

      .container {
        max-width: 800px;
        margin: 0 auto;
      }

      header {
        text-align: center;
        margin-bottom: 40px;
        padding: 20px;
        background: var(--secondary);
        color: var(--primary);
        border-radius: 8px;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
      }

      h1 {
        margin-bottom: 10px;
      }

      .demo-grid {
        display: grid;
        grid-template-columns: 1fr;
        gap: 20px;
      }

      @media (min-width: 600px) {
        .demo-grid {
          grid-template-columns: 1fr 1fr;
        }
      }

      .card {
        background: var(--card-bg);
        border: 1px solid var(--border);
        border-radius: 8px;
        padding: 20px;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
        transition: transform 0.2s;
      }

      .card:hover {
        border: solid rgb(133, 133, 133) thin;
      }

      .card h2 {
        font-size: 1.2rem;
        margin-bottom: 15px;
        color: var(--secondary);
        border-bottom: 2px solid var(--primary);
        display: inline-block;
      }

      .controls {
        display: flex;
        align-items: center;
        gap: 10px;
        margin-bottom: 15px;
      }

      button {
        padding: 8px 16px;
        border: none;
        border-radius: 4px;
        background-color: var(--secondary);
        color: white;
        cursor: pointer;
        font-weight: bold;
        transition: opacity 0.2s;
      }

      button:hover {
        opacity: 0.9;
      }

      button.secondary {
        background-color: var(--primary);
        color: var(--secondary);
      }

      input[type='text'] {
        width: 100%;
        padding: 8px;
        border: 1px solid var(--border);
        border-radius: 4px;
        margin-bottom: 10px;
      }

      .state-display {
        font-family: monospace;
        background: #eee;
        padding: 5px 10px;
        border-radius: 4px;
        font-size: 0.9rem;
      }

      .code-block {
        background: #282c34;
        color: #abb2bf;
        padding: 10px;
        border-radius: 4px;
        font-size: 0.75rem;
        margin-top: 15px;
        overflow-x: auto;
        white-space: pre;
      }

      .highlight {
        color: var(--primary);
      }

      .theme-preview {
        height: 60px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 4px;
        margin-top: 10px;
        border: 1px solid var(--border);
      }

      .theme-dark {
        background-color: #333;
        color: #fff;
      }

      .theme-light {
        background-color: #fff;
        color: #333;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <header>
        <h1>Dom Reactivity Demo</h1>
        <p>Direct document object model manipulation to simulate reactivity.</p>
      </header>

      <div class="demo-grid">
        <!-- Counter Example -->
        <section class="card" id="counter-card">
          <h2>1. Simple Counter</h2>
          <p>State is a number that increments or decrements.</p>
          <div class="controls">
            <button onclick="updateCounter(-1)">-</button>
            <span class="state-display" id="counter-val">0</span>
            <button onclick="updateCounter(1)">+</button>
          </div>
          <div class="code-block">
            state.count += amount;
            const counterEl = document.getElementById('counter-val');
            <span class="highlight">counterEl.textContent = state.count;</span>
          </div>
        </section>

        <!-- Input Example -->
        <section class="card" id="input-card">
          <h2>2. Controlled Input</h2>
          <p>State syncs with the input field value in real-time.</p>
          <input type="text" id="text-input" placeholder="Type something..." oninput="updateText(this.value)" />
          <div class="state-display">Value: <span id="text-val">...</span></div>
          <div class="code-block">
            state.text = val;
            const textEl = document.getElementById('text-val');
            <span class="highlight">textEl.textContent = state.text || '...';</span>
          </div>
        </section>

        <!-- Toggle Example -->
        <section class="card" id="toggle-card">
          <h2>3. Boolean Toggle</h2>
          <p>State manages a true/false value to switch styles.</p>
          <button class="secondary" onclick="toggleTheme()">Switch Theme</button>
          <div id="theme-box" class="theme-preview theme-light">Current: Light</div>
          <div class="code-block">
            state.isDark = !state.isDark;
            const themeClass = state.isDark ? 'theme-dark' : 'theme-light';
            <span class="highlight">box.className = `theme-preview ${themeClass}`;</span>
          </div>
        </section>

        <!-- List Example -->
        <section class="card" id="list-card">
          <h2>4. Array State</h2>
          <p>Adding items to an array in state.</p>
          <button onclick="addItem()">Add Random Item</button>
          <ul id="item-list" style="margin-top: 10px; list-style: none; font-size: 0.8rem"></ul>
          <div class="code-block">
            state.items = [...state.items, randomFruit];
            const li = document.createElement('li');
            li.textContent = item;
            <span class="highlight">listEl.appendChild(li);</span>
          </div>
        </section>
      </div>

      <footer style="margin-top: 40px; text-align: center; font-size: 0.8rem; color: #666">
        <p>This demo uses Vanilla JavaScript to simulate React's <code>useState</code> behavior.</p>
        <p>State → Render → UI Update</p>
      </footer>
    </div>

    <script>
      /**
       * REACT STATE SIMULATION LOGIC
       * In React, changing state triggers a re-render of the component.
       * Here, we simulate that by calling a "render" function after
       * every state update.
       */

      // Initial State Object
      const state = {
        count: 0,
        text: '',
        isDark: false,
        items: [],
      };

      // 1. Counter Logic
      function updateCounter(amount) {
        state.count += amount;
        renderCounter();
      }

      function renderCounter() {
        document.getElementById('counter-val').textContent = state.count;
      }

      // 2. Text Input Logic
      function updateText(val) {
        state.text = val;
        renderText();
      }

      function renderText() {
        const display = document.getElementById('text-val');
        display.textContent = state.text || '...';
      }

      // 3. Theme Toggle Logic
      function toggleTheme() {
        state.isDark = !state.isDark;
        renderTheme();
      }

      function renderTheme() {
        const box = document.getElementById('theme-box');
        if (state.isDark) {
          box.className = 'theme-preview theme-dark';
          box.textContent = 'Current: Dark';
        } else {
          box.className = 'theme-preview theme-light';
          box.textContent = 'Current: Light';
        }
      }

      // 4. List Logic
      function addItem() {
        const fruits = ['🍎 Apple', '🍌 Banana', '🍒 Cherry', '🍇 Grape', '🥝 Kiwi'];
        const randomFruit = fruits[Math.floor(Math.random() * fruits.length)];

        // React best practice: Treat state as immutable (create a new array)
        state.items = [...state.items, randomFruit];
        renderList();
      }

      function renderList() {
        const listEl = document.getElementById('item-list');
        listEl.innerHTML = ''; // Clear current UI

        // Re-render based on current state array
        state.items.forEach((item, index) => {
          const li = document.createElement('li');
          li.textContent = item;
          li.style.animation = 'fadeIn 0.3s ease';
          listEl.appendChild(li);
        });
      }

      // Initial Render
      function init() {
        renderCounter();
        renderText();
        renderTheme();
        renderList();
      }

      // Run on load
      window.onload = init;
    </script>

    <style>
      /* Animation for list items */
      @keyframes fadeIn {
        from {
          opacity: 0;
          transform: translateX(-10px);
        }
        to {
          opacity: 1;
          transform: translateX(0);
        }
      }
    </style>
  </body>
</html>

~~~
```



```masteryls
{"id":"92535d2e-1a6e-4de3-8591-46b7b552dc5e", "title":"React state", "type":"ai-web-page", "gradingCriteria":"React state demonstrated", "height":500 }
Demonstrate how React state hooks work. 

~~~html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>React Reactivity Demo</title>
    <style>
      :root {
        --primary: #fbdc9e;
        --secondary: #282c34;
        --text: #333;
        --bg: #f4f7f6;
        --card-bg: #ffffff;
        --border: #ddd;
        --success: #4caf50;
      }

      * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
      }

      body {
        font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
        line-height: 1.6;
        color: var(--text);
        background-color: var(--bg);
        padding: 20px;
      }

      .container {
        max-width: 800px;
        margin: 0 auto;
      }

      header {
        text-align: center;
        margin-bottom: 40px;
        padding: 20px;
        background: var(--secondary);
        color: var(--primary);
        border-radius: 8px;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
      }

      h1 {
        margin-bottom: 10px;
      }

      .demo-grid {
        display: grid;
        grid-template-columns: 1fr;
        gap: 20px;
      }

      @media (min-width: 600px) {
        .demo-grid {
          grid-template-columns: 1fr 1fr;
        }
      }

      .card {
        background: var(--card-bg);
        border: 1px solid var(--border);
        border-radius: 8px;
        padding: 20px;
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
        transition: transform 0.2s;
      }

      .card:hover {
        border: solid rgb(133, 133, 133) thin;
      }

      .card h2 {
        font-size: 1.2rem;
        margin-bottom: 15px;
        color: var(--secondary);
        border-bottom: 2px solid var(--primary);
        display: inline-block;
      }

      .controls {
        display: flex;
        align-items: center;
        gap: 10px;
        margin-bottom: 15px;
      }

      button {
        padding: 8px 16px;
        border: none;
        border-radius: 4px;
        background-color: var(--secondary);
        color: white;
        cursor: pointer;
        font-weight: bold;
        transition: opacity 0.2s;
      }

      button:hover {
        opacity: 0.9;
      }

      button.secondary {
        background-color: var(--primary);
        color: var(--secondary);
      }

      input[type='text'] {
        width: 100%;
        padding: 8px;
        border: 1px solid var(--border);
        border-radius: 4px;
        margin-bottom: 10px;
      }

      .state-display {
        font-family: monospace;
        background: #eee;
        padding: 5px 10px;
        border-radius: 4px;
        font-size: 0.9rem;
      }

      .code-block {
        background: #282c34;
        color: #abb2bf;
        padding: 10px;
        border-radius: 4px;
        font-size: 0.75rem;
        margin-top: 15px;
        overflow-x: auto;
        white-space: pre;
      }

      .highlight {
        color: var(--primary);
      }

      .theme-preview {
        height: 60px;
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 4px;
        margin-top: 10px;
        border: 1px solid var(--border);
      }

      .theme-dark {
        background-color: #333;
        color: #fff;
      }

      .theme-light {
        background-color: #fff;
        color: #333;
      }

      /* Animation for list items */
      @keyframes fadeIn {
        from {
          opacity: 0;
          transform: translateX(-10px);
        }
        to {
          opacity: 1;
          transform: translateX(0);
        }
      }

      .list-item {
        animation: fadeIn 0.3s ease;
      }
    </style>
  </head>
  <body>
    <div id="root"></div>

    <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

    <script type="text/babel">
      const { useState } = React;

      function ReactReactivityDemo() {
        const [count, setCount] = useState(0);
        const [text, setText] = useState('');
        const [isDark, setIsDark] = useState(false);
        const [items, setItems] = useState([]);

        const fruits = ['🍎 Apple', '🍌 Banana', '🍒 Cherry', '🍇 Grape', '🥝 Kiwi'];

        function addItem() {
          const randomFruit = fruits[Math.floor(Math.random() * fruits.length)];
          setItems((prevItems) => [...prevItems, randomFruit]);
        }

        return (
          <div className="container">
            <header>
              <h1>React Reactivity Demo</h1>
              <p>React state hooks automatically trigger UI updates.</p>
            </header>

            <div className="demo-grid">
              <section className="card" id="counter-card">
                <h2>1. Simple Counter</h2>
                <p>State is a number that increments or decrements.</p>
                <div className="controls">
                  <button onClick={() => setCount((prev) => prev - 1)}>-</button>
                  <span className="state-display" id="counter-val">
                    {count}
                  </span>
                  <button onClick={() => setCount((prev) => prev + 1)}>+</button>
                </div>
                <div className="code-block">
                  {'const [count, setCount] = useState(0);\n'}
                  <span className="highlight">setCount(count + 1);</span>
                </div>
              </section>

              <section className="card" id="input-card">
                <h2>2. Controlled Input</h2>
                <p>State syncs with the input field value in real-time.</p>
                <input type="text" id="text-input" placeholder="Type something..." value={text} onChange={(e) => setText(e.target.value)} />
                <div className="state-display">
                  Value: <span id="text-val">{text || '...'}</span>
                </div>
                <div className="code-block">
                  {'const [text, setText] = useState("");\n'}
                  <span className="highlight">onChange={(e) => setText(e.target.value)}</span>
                </div>
              </section>

              <section className="card" id="toggle-card">
                <h2>3. Boolean Toggle</h2>
                <p>State manages a true/false value to switch styles.</p>
                <button className="secondary" onClick={() => setIsDark((prev) => !prev)}>
                  Switch Theme
                </button>
                <div id="theme-box" className={`theme-preview ${isDark ? 'theme-dark' : 'theme-light'}`}>
                  {`Current: ${isDark ? 'Dark' : 'Light'}`}
                </div>
                <div className="code-block">
                  {'const [isDark, setIsDark] = useState(false);\n'}
                  <span className="highlight">className={isDark ? 'dark' : 'light'}</span>
                </div>
              </section>

              <section className="card" id="list-card">
                <h2>4. Array State</h2>
                <p>Adding items to an array in state.</p>
                <button onClick={addItem}>Add Random Item</button>
                <ul id="item-list" style={{ marginTop: '10px', listStyle: 'none', fontSize: '0.8rem' }}>
                  {items.map((item, index) => (
                    <li key={`${item}-${index}`} className="list-item">
                      {item}
                    </li>
                  ))}
                </ul>
                <div className="code-block">
                  {'const [items, setItems] = useState([]);\n'}
                  <span className="highlight">setItems([...items, newItem]);</span>
                </div>
              </section>
            </div>

            <footer style={{ marginTop: '40px', textAlign: 'center', fontSize: '0.8rem', color: '#666' }}>
              <p>
                This demo uses React and <code>useState</code> for reactivity.
              </p>
              <p>State → Render → UI Update</p>
            </footer>
          </div>
        );
      }

      const root = ReactDOM.createRoot(document.getElementById('root'));
      root.render(<ReactReactivityDemo />);
    </script>
  </body>
</html>

~~~
```


```masteryls
{"id":"aea2c9b9-bf13-4019-a5d2-363da735f3e0", "title":"Web page", "type":"web-page", "height":250}
  <body style="margin:0;display:grid;place-items:center;min-height:100vh;background:radial-gradient(circle at 20% 20%,#22d3ee,#0f172a);color:#ecfeff;font-family:ui-monospace,monospace;">
    <h1 style="font-size:clamp(1.4rem,4vw,2.4rem);letter-spacing:.06em;">Hello, curious learner.</h1>
  </body>
```


```masteryls
{"id":"b0c3c187-8e65-4d4f-9f60-b2aae1941d04", "title":"Web page development", "type":"ai-web-page", "gradingCriteria":"The word 'byu' must be included in the HTML.", "height":500 }
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