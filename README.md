# ai-tools-website
My Free AI Tools Website
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>AI Tools Hub</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #0f172a;
      color: white;
      text-align: center;
    }

    header {
      padding: 25px 15px;
      background: #1e293b;
    }

    header h1 {
      color: #38bdf8;
      margin-bottom: 10px;
    }

    .container {
      padding: 20px;
      max-width: 800px;
      margin: auto;
    }

    .tools {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 15px;
    }

    .card {
      background: #1e293b;
      padding: 20px;
      border-radius: 12px;
      text-align: left;
    }

    textarea, input {
      width: 100%;
      padding: 12px;
      margin: 8px 0;
      border-radius: 8px;
      border: none;
      font-size: 16px;
    }

    button {
      background: #38bdf8;
      color: #0f172a;
      border: none;
      padding: 12px 16px;
      border-radius: 8px;
      font-weight: bold;
      cursor: pointer;
    }

    .result {
      white-space: pre-wrap;
      overflow-wrap: anywhere;
      margin-top: 12px;
      color: #bae6fd;
    }

    footer {
      padding: 20px;
      color: #94a3b8;
    }
  </style>
</head>

<body>

  <header>
    <h1>🤖 AI Tools Hub</h1>
    <p>Your All-in-One AI Tools Website</p>
  </header>

  <main class="container">
    <h2>Explore Our Tools</h2>

    <div class="tools">

      <section class="card">
        <h3>✍️ AI Writer</h3>
        <p>Write ideas, stories and content.</p>
        <textarea id="writerInput" placeholder="Enter a topic..."></textarea>
        <button onclick="writeText()">Generate Text</button>
        <div class="result" id="writerResult"></div>
      </section>

      <section class="card">
        <h3>📝 Text Summarizer</h3>
        <p>Create a short summary of your text.</p>
        <textarea id="summaryInput" placeholder="Paste your text..."></textarea>
        <button onclick="summarizeText()">Summarize</button>
        <div class="result" id="summaryResult"></div>
      </section>

      <section class="card">
        <h3>💬 AI Chat</h3>
        <p>Ask a question or explore an idea.</p>
        <input id="chatInput" placeholder="Type your question...">
        <button onclick="chat()">Ask</button>
        <div class="result" id="chatResult"></div>
      </section>

    </div>
  </main>

  <footer>
    Made with ❤️ | AI Tools Hub
  </footer>

  <script>
    function writeText() {
      const topic = document.getElementById("writerInput").value.trim();

      document.getElementById("writerResult").textContent = topic
        ? "Your topic: " + topic +
          "\n\nConnect an AI API to generate real AI-written content."
        : "Please enter a topic.";
    }

    function summarizeText() {
      const text = document.getElementById("summaryInput").value.trim();

      if (!text) {
        document.getElementById("summaryResult").textContent =
          "Please enter some text.";
        return;
      }

      const sentences = text.match(/[^.!?]+[.!?]*/g) || [text];
      const summary = sentences.slice(0, 2).join(" ");

      document.getElementById("summaryResult").textContent =
        "Quick summary:\n" + summary;
    }

    function chat() {
      const question = document.getElementById("chatInput").value.trim();

      document.getElementById("chatResult").textContent = question
        ? "Your question: " + question +
          "\n\nConnect an AI API to get real AI answers."
        : "Please enter a question.";
    }
  </script>

</body>
</html>
