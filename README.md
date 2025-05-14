  <h1>🤖 Telegram Bot: Анкета + Redis</h1>

  <p>Этот Telegram-бот позволяет пользователю заполнить мини-анкету (имя и возраст), сохранить её на сервере в Redis и при необходимости просмотреть сохранённые данные.</p>

  <h2>🧰 Стек технологий</h2>
  <ul>
    <li>Python</li>
    <li>Telegram Bot API (через <code>requests</code>)</li>
    <li>Flask (backend)</li>
    <li>Redis (через <code>redis-py</code>)</li>
  </ul>

  <h2>🚀 Как запустить</h2>

  <h3>1. Клонируй репозиторий</h3>
  <pre><code>git clone https://github.com/your-username/telegram-form-bot.git
cd telegram-form-bot</code></pre>

  <h3>2. Установи зависимости</h3>
  <pre><code>pip install -r requirements.txt</code></pre>

  <p><strong>Пример содержимого <code>requirements.txt</code>:</strong></p>
  <pre><code>flask
redis
requests</code></pre>

  <h3>3. Запусти Redis</h3>
  <pre><code>redis-server</code></pre>

  <p><em>Или с Docker:</em></p>
  <pre><code>docker run --name redis-bot -p 6379:6379 redis</code></pre>

  <h3>4. Запусти backend-сервер</h3>
  <pre><code>python backend.py</code></pre>

  <p>Он будет слушать по адресу <code>http://localhost:5000</code>.</p>

  <h3>5. Запусти Telegram-бота</h3>
  <pre><code>python bot.py</code></pre>

  <h2>💬 Команды бота</h2>
  <ul>
    <li><code>/start</code> — начать работу с ботом, отобразить меню</li>
    <li><code>/help</code> — показать справку по командам</li>
    <li><code>/show</code> — показать заполненную анкету (если уже была сохранена)</li>
  </ul>

  <h2>🗃️ Структура хранения в Redis</h2>
  <p>Анкеты пользователей сохраняются как Hash с ключом <code>user:{telegram_user_id}</code>:</p>
  <pre><code>HGETALL user:123456789</code></pre>

  <p>Пример:</p>
  <pre><code>"user_id" -> "123456789"
"name"    -> "Arthur"
"age"     -> "18"</code></pre>

  <h2>📌 Примечания</h2>
  <ul>
    <li>Убедись, что backend и Redis работают <strong>локально</strong>, либо укажи их адрес в коде (<code>http://localhost:5000</code>).</li>
    <li>Токен Telegram-бота указывается в переменной <code>TOKEN</code> в <code>bot.py</code>.</li>
  </ul>
