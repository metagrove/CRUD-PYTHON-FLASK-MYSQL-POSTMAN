# 📇 Contact Management System – CRUDdy but Delightful!

Hello there, fellow coder! 👋 Welcome to **Contact Management System**, a tiny yet mighty Flask + MySQL API that lets you Create, Read, Update & Delete (CRUD) your friends’ (or frenemies’) contact info faster than you can say “new phone, who dis?”

> **Why another CRUD?** Because practice makes perfect, and everyone needs *at least one* project that saves phone numbers in a database. Plus… databases are cool. 🕶️

---

## 🚀 Quick Start

```bash
# 1. Clone the repo (we won’t tell your boss)
$ git clone https://github.com/your‑handle/contact‑management‑system.git
$ cd contact‑management‑system

# 2. Create and activate a venv (optional but highly recommended)
$ python -m venv venv
$ source venv/bin/activate   # On Windows: venv\Scripts\activate

# 3. Install requirements
$ pip install -r requirements.txt

# 4. Make sure MySQL is running and create the DB
mysql> CREATE DATABASE contact_db;

# 5. Launch 🎬
$ python app.py

# Voilà! Visit http://127.0.0.1:5000/ to get your welcome message.
```

---

## ⚙️ Configuration

The connection string lives in `app.py`:

```python
app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql+pymysql://root:password@localhost:3306/contact_db'
```

Change `root` and `password` to match your local creds (or better yet, chuck them in environment variables – your future self will thank you).

---

## 🛣️ Endpoints at a Glance

| Method | Endpoint                | Purpose                           |
| ------ | ----------------------- | --------------------------------- |
| GET    | `/`                     | Health check & warm greeting      |
| POST   | `/add_contacts/`        | Add a shiny new contact ✨         |
| GET    | `/read_contacts/`       | Retrieve the whole contact list   |
| PUT    | `/update_contacts/<id>` | Update one lucky contact by ID    |
| DELETE | `/delete_contacts/<id>` | Banish a contact into oblivion 🚮 |

> **NOTE:** Requests and responses are in glorious JSON. Send `Content‑Type: application/json` unless you enjoy 400 errors.

---

## 🛠️ Sample Payloads

### Create a Contact

```json
{
  "name": "Mario Mario",
  "age": 35,
  "email": "mario@nintendo.it",
  "phone": "+39 555‑MUSHROOM"
}
```

### Update a Contact (Partial OK!)

```json
{
  "phone": "+39 555‑1UP‑LIFE"
}
```

---

## 📂 Project Structure

```
├── app.py          # Flask application (a.k.a. the brains 🧠)
├── requirements.txt
└── README.md       # You are here!
```

Feel free to sprinkle in Blueprints, tests, Docker, or whatever floats your boat. This repo is your playground! 🛝

---

## 🧪 Testing with cURL (Postman optional)

```bash
# Add a contact
curl -X POST http://127.0.0.1:5000/add_contacts/ \
  -H "Content-Type: application/json" \
  -d '{"name":"Lara Croft","age":29,"email":"lara@croft.co","phone":"+44 555‑RAIDER"}'

# Read all contacts
curl http://127.0.0.1:5000/read_contacts/

# Update Lara (id=1 for example)
curl -X PUT http://127.0.0.1:5000/update_contacts/1 \
  -H "Content-Type: application/json" \
  -d '{"age": 30}'

# Delete Lara
curl -X DELETE http://127.0.0.1:5000/delete_contacts/1
```

---

## 🤝 Contributing

1. Fork 🍴
2. Create a feature branch (`git checkout -b feature/slash‑command`)
3. Commit something amazing (`git commit -m "✨ Add unicorn endpoint"`)
4. Push and open a PR – we’ll high‑five you in emojis. 🙌

---

## 📝 License

MIT. Do what you want, but if it breaks, you *get* to keep both halves. 😉

---

### ✨ Final Words

Life is better with well‑managed contacts. May your 200 responses be ever in your favor, and your 500s be few and far between. Happy hacking! 🎉
