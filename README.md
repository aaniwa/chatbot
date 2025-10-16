# ChatBot (Flask + Groq)

Simple web chat UI served by a Flask app that forwards user messages to a Groq chat model.

## Quick start

1. Install dependencies:
```sh
pip install -r requirements.txt
```

2. Edit your API key in [app.py](app.py):
- Replace `Groq(api_key="key-xxxxxx")` with your real key.

3. Run the app:
```sh
python app.py
```

4. Open the chat UI:
- Visit http://127.0.0.1:5000/chatbot

## Endpoints

- GET /chatbot — serves the chat page (see [`chatbot_page`](app.py))
- GET /get?msg=... — returns JSON with `reply` from the model (see [`get_msg`](app.py))
- Internal helper: [`ask_groq`](app.py) — sends prompts to Groq

## Project layout

- [app.py](app.py) — Flask server and route handlers
- [requirements.txt](requirements.txt) — Python dependencies
- [templates/chatbot.html](templates/chatbot.html) — client HTML/JS UI
- [static/styles/style.css](static/styles/style.css) — UI styles

## Notes

- The UI uses jQuery and marked.js to send messages and render simple markdown.
- Ensure your Groq model name and API key are valid in [app.py](app.py).
- The chat endpoint returns raw model output as `reply` in JSON.

## Troubleshooting

- If the app returns errors from the Groq call, check the exception message printed by the `/get` route and verify network/API credentials.
- If static assets don't load, confirm Flask's `static` and `templates` folders are present and unchanged.

## License

MIT (adjust as needed)
