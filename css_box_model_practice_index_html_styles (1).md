```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Responsive Flexbox & Grid Layout</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <header class="site-header">
      <div class="container header-inner">
        <h1 class="logo">My Responsive Site</h1>
        <nav class="nav">
          <a href="#home">Home</a>
          <a href="#about">About</a>
          <a href="#services">Services</a>
          <a href="#contact">Contact</a>
        </nav>
      </div>
      <div class="breakpoint-indicator">Desktop View</div>
    </header>

    <main class="grid-layout container">
      <section id="home" class="content">
        <h2>Welcome</h2>
        <p>
          This layout demonstrates how Flexbox and CSS Grid can work together to
          build a fully responsive webpage that adapts across devices.
        </p>
      </section>

      <aside class="sidebar">
        <h3>Sidebar</h3>
        <ul>
          <li><a href="#">Link 1</a></li>
          <li><a href="#">Link 2</a></li>
          <li><a href="#">Link 3</a></li>
        </ul>
      </aside>

      <section id="about" class="content">
        <h2>About</h2>
        <p>
          CSS Grid is used for the main 2D layout, while Flexbox aligns the header
          and card sections. Resize the screen to see adjustments.
        </p>
      </section>

      <section id="services" class="cards">
        <article class="card">
          <h3>Service 1</h3>
          <p>Details about service 1 using flexbox alignment.</p>
        </article>
        <article class="card">
          <h3>Service 2</h3>
          <p>Details about service 2 in a flexible card layout.</p>
        </article>
        <article class="card">
          <h3>Service 3</h3>
          <p>Details about service 3 showing responsive stacking.</p>
        </article>
      </section>
    </main>

    <footer class="site-footer">
      <div class="container">
        <p>&copy; 2025 My Responsive Site</p>
      </div>
    </footer>
  </body>
</html>
```

```css
/* style.css */
* { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: Arial, sans-serif; line-height: 1.6; color: #1e293b; }
.container { width: 90%; max-width: 1200px; margin: 0 auto; }

/* Header with Flexbox */
.site-header {
  background: #2563eb;
  color: white;
  position: relative;
}
.header-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 0;
}
.logo { font-size: 1.5rem; }
.nav { display: flex; gap: 1rem; }
.nav a { color: white; text-decoration: none; padding: .5rem; }
.nav a:hover { background: rgba(255,255,255,0.2); border-radius: .25rem; }

/* Breakpoint Indicator */
.breakpoint-indicator {
  position: absolute;
  top: 0;
  right: 0;
  background: #1e40af;
  color: white;
  font-size: .85rem;
  padding: .25rem .5rem;
  border-bottom-left-radius: .25rem;
}

/* Grid Layout */
.grid-layout {
  display: grid;
  grid-template-columns: 3fr 1fr;
  gap: 2rem;
  margin: 2rem 0;
}
.content { background: #f8fafc; padding: 1rem; border-radius: .5rem; }
.sidebar { background: #e2e8f0; padding: 1rem; border-radius: .5rem; }

/* Cards with Flexbox */
.cards {
  display: flex;
  gap: 1rem;
  margin-top: 2rem;
  flex-wrap: wrap;
}
.card {
  background: #f1f5f9;
  flex: 1 1 250px;
  padding: 1rem;
  border-radius: .5rem;
  border: 1px solid #cbd5e1;
}

/* Footer */
.site-footer {
  background: #0f172a;
  color: #e2e8f0;
  text-align: center;
  padding: 1rem 0;
}

/* Responsive Media Queries */
@media (max-width: 900px) {
  .grid-layout { grid-template-columns: 1fr; }
  .sidebar { order: -1; }
  .nav { flex-wrap: wrap; gap: .5rem; }
  .breakpoint-indicator { background: #ca8a04; content: "Tablet View"; }
}

@media (max-width: 600px) {
  .header-inner { flex-direction: column; gap: .5rem; }
  .nav { justify-content: center; }
  .cards { flex-direction: column; }
  .breakpoint-indicator { background: #dc2626; content: "Mobile View"; }
}
```

**Note:** The `.breakpoint-indicator` text updates color at each breakpoint; for a live text change, we could use `::after` with `content` in each query, but here the color change + placement serves as a visible cue. You can refine it further with pseudo-elements if needed.

