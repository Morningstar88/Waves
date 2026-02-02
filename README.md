# Waves

# 2026 Reboot. 

### Yo Skippy! Where

## V 0.1

https://jsfiddle.net/p9t6L0bq/

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Contact Jack Maclavity</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      margin: 0;
      padding: 0;
    }
    header {
      background: #4a148c;
      color: white;
      padding: 1rem;
      text-align: center;
    }
    .container {
      max-width: 600px;
      margin: 2rem auto;
      background: white;
      padding: 2rem;
      border-radius: 8px;
      box-shadow: 0 2px 6px rgba(0,0,0,0.2);
    }
    form {
      display: flex;
      flex-direction: column;
    }
    label {
      margin-top: 1rem;
      font-weight: bold;
    }
    input, textarea {
      padding: 0.5rem;
      margin-top: 0.5rem;
      border: 1px solid #ccc;
      border-radius: 4px;
      font-size: 1rem;
    }
    button {
      margin-top: 1.5rem;
      padding: 0.75rem;
      background: #4a148c;
      color: white;
      border: none;
      border-radius: 4px;
      font-size: 1rem;
      cursor: pointer;
    }
    button:hover {
      background: #6a1b9a;
    }
    .messages {
      margin-top: 2rem;
    }
    .message {
      border-bottom: 1px solid #eee;
      padding: 0.5rem 0;
    }
    .message strong {
      color: #4a148c;
    }
  </style>
</head>
<body>
  <header>
    <h1>Message Jack Maclavity in Siem Reap</h1>
    <p>Friends and listeners can send him a note</p>
  </header>
  <div id="root" class="container"></div>

  <!-- React and Babel CDN -->
  <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
  <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
  <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>

  <!-- React App -->
  <script type="text/babel">
    function ContactFormApp() {
      const [name, setName] = React.useState("");
      const [message, setMessage] = React.useState("");
      const [messages, setMessages] = React.useState([]);

      const handleSubmit = (e) => {
        e.preventDefault();
        if (!name.trim() || !message.trim()) return;
        const newMsg = { sender: name, text: message };
        setMessages([newMsg, ...messages]);
        setName("");
        setMessage("");
      };

      return (
        <div>
          <form onSubmit={handleSubmit}>
            <label>Your Name</label>
            <input
              type="text"
              value={name}
              onChange={(e) => setName(e.target.value)}
              placeholder="Enter your name"
            />
            <label>Your Message</label>
            <textarea
              rows="4"
              value={message}
              onChange={(e) => setMessage(e.target.value)}
              placeholder="Write your message to Jack..."
            ></textarea>
            <button type="submit">Send Message</button>
          </form>

          <div className="messages">
            <h2>Messages to Jack</h2>
            {messages.length === 0 && <p>No messages yet.</p>}
            {messages.map((msg, idx) => (
              <div key={idx} className="message">
                <strong>{msg.sender}:</strong> {msg.text}
              </div>
            ))}
          </div>
        </div>
      );
    }

    ReactDOM.render(<ContactFormApp />, document.getElementById("root"));
  </script>
</body>
</html>


Private messages that wipe after 7 days

We forked Messengyr last night:

https://github.com/Microflow/messengyr

## 2 Key Features

1. Messages will wipe after 7 days. Saves us database space. Gives more privacy to the user.
2. We'll work hard on the CSS and make some beautiful UI's, like Slack did for IRC. Codepenners welcome. Right now, we need more JS and CSS people than Elixir. The back-end code is simple but solid.
List of issues + features here:

https://github.com/Microflow/Waves/issues

I don't want to use any external, corporate APIs from FB, Amazon or Google if possible. We'll tell our user their messages are private. We can look at encryption later.

## Submission Guidelines

No docs yet, but please ask before using a framework. Vue JS and Mithril are welcome for now. Vanilla JS and HTML is fine as well. Would prefer not to use React JS or any other big tech framework. Keep the web independent.

We're looking for kind, cooperative people. Everyone's welcome. Beginners can help research codepens, APIs and help write docs.

We'll communicate on this thread, or Github issues.

<p align="center">
 <a href="https://messengyr.herokuapp.com">
  <img src="https://cloud.githubusercontent.com/assets/2598660/23702379/3f268fe6-03fb-11e7-822d-46a85e43bc4e.png" width="400" />
 </a>
</p>

<p align="center">
A clone of <a href="http://messenger.com">Facebook Messenger</a>. <br>
Built with <a href="http://elixir-lang.org">Elixir</a> and the <a href="http://www.phoenixframework.org">Phoenix framework</a>.
</p>


----

<p align="center">
 <a href="https://messengyr.herokuapp.com">
 <strong>DEMO</strong>
 </a>
 <br><br>
 Want to learn how to build this?
 <a href="https://www.ludu.co/course/discover-elixir-phoenix">Check out my course on Ludu</a>!
</p>
