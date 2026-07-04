<!doctype html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Interactive Task & Reward Board</title>
  <style>
    :root {
      --bg1: #f6e9ff;
      --bg2: #e7f7ff;
      --card: #ffffff;
      --ink: #2f2540;
      --muted: #7a6c8c;
      --accent: #9b7bff;
      --accent2: #61c7ff;
      --done: #50c878;
      --shadow: 0 12px 28px rgba(67, 38, 113, 0.18);
    }

    * { box-sizing: border-box; }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
      color: var(--ink);
      background:
        radial-gradient(circle at top left, rgba(155,123,255,.35), transparent 30%),
        radial-gradient(circle at bottom right, rgba(97,199,255,.45), transparent 30%),
        linear-gradient(135deg, var(--bg1), var(--bg2));
      padding: 32px;
    }

    .app {
      width: min(1100px, 100%);
      margin: 0 auto;
    }

    header {
      display: flex;
      justify-content: space-between;
      gap: 20px;
      align-items: end;
      margin-bottom: 24px;
    }

    h1 {
      margin: 0;
      font-size: clamp(2rem, 4vw, 4rem);
      letter-spacing: -0.06em;
      line-height: .95;
    }

    .subtitle {
      margin-top: 10px;
      color: var(--muted);
      font-size: 1rem;
    }

    .panel {
      background: rgba(255,255,255,.72);
      border: 1px solid rgba(255,255,255,.75);
      border-radius: 22px;
      box-shadow: var(--shadow);
      padding: 16px;
      min-width: 220px;
      backdrop-filter: blur(12px);
    }

    .score {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
      text-align: center;
    }

    .score div {
      background: white;
      border-radius: 16px;
      padding: 12px;
    }

    .score strong {
      display: block;
      font-size: 1.7rem;
    }

    .score span {
      color: var(--muted);
      font-size: .82rem;
    }

    .controls {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin: 18px 0 24px;
    }

    button, input {
      font: inherit;
    }

    button {
      border: 0;
      border-radius: 999px;
      background: var(--ink);
      color: white;
      padding: 11px 16px;
      cursor: pointer;
      box-shadow: 0 8px 18px rgba(47,37,64,.18);
      transition: transform .15s ease, opacity .15s ease;
    }

    button:hover { transform: translateY(-1px); }
    button:active { transform: translateY(1px); }

    button.secondary {
      background: white;
      color: var(--ink);
    }

    .board {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(190px, 1fr));
      gap: 18px;
    }

    .tile {
      height: 210px;
      perspective: 1000px;
    }

    .tile-inner {
      position: relative;
      width: 100%;
      height: 100%;
      transition: transform .65s cubic-bezier(.2,.8,.2,1);
      transform-style: preserve-3d;
      cursor: pointer;
    }

    .tile.revealed .tile-inner {
      transform: rotateY(180deg);
    }

    .face {
      position: absolute;
      inset: 0;
      padding: 18px;
      border-radius: 26px;
      backface-visibility: hidden;
      box-shadow: var(--shadow);
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      overflow: hidden;
    }

    .front {
      background: linear-gradient(145deg, rgba(255,255,255,.95), rgba(255,255,255,.74));
      border: 1px solid rgba(255,255,255,.9);
    }

    .front::after {
      content: "";
      position: absolute;
      width: 130px;
      height: 130px;
      right: -50px;
      bottom: -50px;
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      border-radius: 999px;
      opacity: .35;
    }

    .back {
      transform: rotateY(180deg);
      background: linear-gradient(145deg, #fff8d8, #ffdff3);
      border: 1px solid rgba(255,255,255,.9);
      text-align: center;
      align-items: center;
    }

    .tag {
      width: fit-content;
      font-size: .75rem;
      color: white;
      background: linear-gradient(135deg, var(--accent), var(--accent2));
      padding: 7px 10px;
      border-radius: 999px;
      font-weight: 700;
      letter-spacing: .04em;
      text-transform: uppercase;
      z-index: 1;
    }

    .task {
      font-size: 1.35rem;
      font-weight: 800;
      line-height: 1.1;
      z-index: 1;
    }

    .hint, .reward-note {
      color: var(--muted);
      font-size: .9rem;
      z-index: 1;
    }

    .reward-icon {
      font-size: 3rem;
      margin-top: 6px;
    }

    .reward {
      font-size: 1.35rem;
      font-weight: 900;
      line-height: 1.1;
    }

    .done-pill {
      display: none;
      color: white;
      background: var(--done);
      border-radius: 999px;
      padding: 8px 12px;
      font-size: .8rem;
      font-weight: 800;
    }

    .tile.revealed .done-pill { display: inline-block; }

    .delete-btn {
      align-self: flex-start;
      background: rgba(47,37,64,.1);
      color: var(--ink);
      box-shadow: none;
      padding: 8px 11px;
      font-size: .8rem;
      z-index: 2;
    }

    .empty-state {
      grid-column: 1 / -1;
      text-align: center;
      background: rgba(255,255,255,.78);
      border: 1px dashed rgba(47,37,64,.25);
      color: var(--muted);
      border-radius: 24px;
      padding: 36px 18px;
      box-shadow: var(--shadow);
    }

    .editor {
      margin-top: 28px;
      background: rgba(255,255,255,.75);
      border-radius: 24px;
      padding: 18px;
      box-shadow: var(--shadow);
    }

    .editor h2 { margin: 0 0 12px; }

    .add-row {
      display: grid;
      grid-template-columns: 1fr 1fr auto;
      gap: 10px;
    }

    input {
      width: 100%;
      padding: 12px 14px;
      border: 1px solid rgba(47,37,64,.12);
      border-radius: 16px;
      outline: none;
      background: white;
    }

    input:focus {
      border-color: var(--accent);
      box-shadow: 0 0 0 4px rgba(155,123,255,.13);
    }

    @media (max-width: 700px) {
      body { padding: 18px; }
      header { display: block; }
      .panel { margin-top: 18px; }
      .add-row { grid-template-columns: 1fr; }
      .tile { height: 190px; }
    }
  </style>
</head>
<body>
  <main class="app">
    <header>
      <section>
        <h1>Task Reward Board</h1>
        <p class="subtitle">Add your own tasks and hidden rewards. Finish a task, flip the tile, and reveal what is underneath.</p>
      </section>
      <aside class="panel">
        <div class="score">
          <div><strong id="doneCount">0</strong><span>revealed</span></div>
          <div><strong id="leftCount">0</strong><span>left</span></div>
        </div>
      </aside>
    </header>

    <div class="controls">
      <button id="shuffleBtn">Shuffle rewards</button>
      <button class="secondary" id="resetBtn">Reset board</button>
    </div>

    <section class="board" id="board"></section>

    <section class="editor">
      <h2>Add your custom tile</h2>
      <div class="add-row">
        <input id="taskInput" placeholder="Task, e.g. Clean desk" />
        <input id="rewardInput" placeholder="Hidden reward, e.g. 20 min gaming" />
        <button id="addBtn">Add</button>
      </div>
    </section>
  </main>

  <script>
    const defaultTiles = [];

    let tiles = JSON.parse(localStorage.getItem("taskRewardTiles") || "[]");
    let revealed = JSON.parse(localStorage.getItem("taskRewardRevealed")) || [];

    const board = document.getElementById("board");
    const doneCount = document.getElementById("doneCount");
    const leftCount = document.getElementById("leftCount");

    function save() {
      localStorage.setItem("taskRewardTiles", JSON.stringify(tiles));
      localStorage.setItem("taskRewardRevealed", JSON.stringify(revealed));
    }

    function render() {
      board.innerHTML = "";
      if (tiles.length === 0) {
        board.innerHTML = `<div class="empty-state">Add your own custom task and hidden reward below to create your first tile.</div>`;
      }
      tiles.forEach((item, index) => {
        const tile = document.createElement("article");
        tile.className = "tile" + (revealed.includes(index) ? " revealed" : "");
        tile.innerHTML = `
          <div class="tile-inner" role="button" tabindex="0" aria-label="Reveal reward for ${item.task}">
            <div class="face front">
              <span class="tag">Task ${index + 1}</span>
              <div class="task">${escapeHtml(item.task)}</div>
              <div class="hint">Click when complete to reveal reward</div>
              <button class="delete-btn" data-index="${index}" type="button">Delete</button>
            </div>
            <div class="face back">
              <span class="done-pill">Complete</span>
              <div class="reward-icon">🎁</div>
              <div class="reward">${escapeHtml(item.reward)}</div>
              <div class="reward-note">Reward unlocked</div>
            </div>
          </div>
        `;

        const inner = tile.querySelector(".tile-inner");
        tile.querySelector(".delete-btn").addEventListener("click", event => {
          event.stopPropagation();
          deleteTile(index);
        });

        inner.addEventListener("click", () => toggleReveal(index));
        inner.addEventListener("keydown", event => {
          if (event.key === "Enter" || event.key === " ") {
            event.preventDefault();
            toggleReveal(index);
          }
        });

        board.appendChild(tile);
      });
      updateScore();
      save();
    }

    function toggleReveal(index) {
      if (revealed.includes(index)) {
        revealed = revealed.filter(i => i !== index);
      } else {
        revealed.push(index);
      }
      render();
    }

    function updateScore() {
      doneCount.textContent = revealed.length;
      leftCount.textContent = Math.max(tiles.length - revealed.length, 0);
    }

    function shuffleRewards() {
      const rewards = tiles.map(t => t.reward).sort(() => Math.random() - 0.5);
      tiles = tiles.map((tile, i) => ({ ...tile, reward: rewards[i] }));
      revealed = [];
      render();
    }

    function resetBoard() {
      revealed = [];
      render();
    }

    function deleteTile(index) {
      tiles.splice(index, 1);
      revealed = revealed
        .filter(i => i !== index)
        .map(i => i > index ? i - 1 : i);
      render();
    }

    function addTile() {
      const task = document.getElementById("taskInput").value.trim();
      const reward = document.getElementById("rewardInput").value.trim();
      if (!task || !reward) {
        alert("Please enter both a task and a hidden reward.");
        return;
      }
      tiles.push({ task, reward });
      document.getElementById("taskInput").value = "";
      document.getElementById("rewardInput").value = "";
      render();
    }

    function escapeHtml(text) {
      const div = document.createElement("div");
      div.textContent = text;
      return div.innerHTML;
    }

    document.getElementById("shuffleBtn").addEventListener("click", shuffleRewards);
    document.getElementById("resetBtn").addEventListener("click", resetBoard);
    document.getElementById("addBtn").addEventListener("click", addTile);

    render();
  </script>
</body>
</html>
