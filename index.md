---
title: Chatbot
---

# 🚀 My Chatbot

A friendly chat interface embedded below. If the chat appears blank, make sure the bot's URL allows embedding (no `X-Frame-Options: DENY`).

<div class="page">
  <aside class="meta">
    <h2>About</h2>
    <p>Just paste your abstract for the bot and you'll get a one-sentence summary of it!</p>
    <p><strong>Tip:</strong> press the dark-mode button to switch theme.</p>
    <button id="themeToggle" aria-label="Toggle theme">🌙</button>
  </aside>

  <main class="chat-wrap">
    <div class="chat-card">
      <!-- Your provided iframe (kept allow="microphone" and min-height:700px) -->
      <iframe id="chatFrame"
              src="https://udify.app/chatbot/sI7tIcJbUKYk9pHy"
              style="width:100%; height:100%; min-height:700px; border:0; border-radius:10px;"
              frameborder="0"
              allow="microphone">
      </iframe>
    </div>
  </main>
</div>

<footer class="foot">Made with ❤️ · <small>GitHub Pages</small></footer>

<style>
:root{
  --bg:#f6f7fb; --card:#ffffff; --muted:#5b6470; --accent:#2563eb; --glass: rgba(255,255,255,0.6);
}
[data-theme="dark"]{ --bg:#0b1220; --card:#071029; --muted:#9aa6b2; --accent:#60a5fa; --glass: rgba(255,255,255,0.03); color: #e6eef8; }
*{box-sizing:border-box}
body{font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial; background:var(--bg); margin:28px; color:inherit}
.page{display:grid; grid-template-columns:300px 1fr; gap:20px; align-items:start; max-width:1100px; margin:0 auto}
.meta{background:var(--card); padding:18px; border-radius:14px; box-shadow:0 6px 20px rgba(15,23,42,0.08)}
.meta h2{margin-top:0}
#themeToggle{margin-top:10px; padding:8px 12px; border-radius:10px; border:0; cursor:pointer; background:var(--glass)}
.chat-wrap{display:flex; align-items:flex-start; justify-content:center}
.chat-card{width:100%; min-height:520px; background:var(--card); border-radius:14px; padding:12px; box-shadow:0 8px 30px rgba(12,18,28,0.08); display:flex; flex-direction:column}
iframe{width:100%; height:600px; border:0; border-radius:10px; background:transparent}
.foot{text-align:center; margin-top:18px; color:var(--muted); opacity:.9}

/* Responsive adjustments */
@media (max-width:900px){
  .page{grid-template-columns:1fr; padding:0 14px}
  iframe{height:520px}
  .meta{order:2}
}
</style>

<script>
(function(){
  const btn = document.getElementById('themeToggle');
  const stored = localStorage.getItem('theme');
  if(stored === 'dark') document.documentElement.setAttribute('data-theme','dark');

  btn.addEventListener('click', ()=>{
    const has = document.documentElement.getAttribute('data-theme') === 'dark';
    if(has){
      document.documentElement.removeAttribute('data-theme');
      localStorage.setItem('theme','light');
      btn.textContent='🌙';
    } else {
      document.documentElement.setAttribute('data-theme','dark');
      localStorage.setItem('theme','dark');
      btn.textContent='☀️';
    }
  });
})();
</script>
