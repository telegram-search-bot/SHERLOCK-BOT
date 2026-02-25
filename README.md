# SHERLOCK-BOT
Шерлок тг бот - проверка данных, поиск по номеру телефона, ФИО, OSINT и другое
<!doctype html>
<html lang="ru">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <meta name="theme-color" content="#0b1020" />
  <title>Sherlock TG — OSINT-аудит и цифровая гигиена в Telegram</title>

  <!-- SEO -->
  <meta name="description" content="Sherlock TG — Telegram-бот для аудита цифрового следа и проверки открытых источников: структурированные отчёты, риск-индикаторы, рекомендации по защите аккаунтов." />
  <meta name="robots" content="index,follow" />

  <!-- Open Graph -->
  <meta property="og:title" content="Sherlock TG — OSINT-аудит и цифровая гигиена" />
  <meta property="og:description" content="Проверка открытых источников, структурированные отчёты, рекомендации по защите." />
  <meta property="og:type" content="website" />

  <!-- Tailwind CDN -->
  <script src="https://cdn.tailwindcss.com"></script>

  <style>
    /* небольшая кастомизация, чтобы отличаться от типовых лендингов */
    .noise:before{
      content:"";
      position:absolute; inset:0;
      background-image:url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='140' height='140'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.8' numOctaves='3' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='140' height='140' filter='url(%23n)' opacity='.15'/%3E%3C/svg%3E");
      opacity:.35; mix-blend-mode:overlay; pointer-events:none;
    }
    .gridlines{
      background-image:
        linear-gradient(to right, rgba(255,255,255,.06) 1px, transparent 1px),
        linear-gradient(to bottom, rgba(255,255,255,.06) 1px, transparent 1px);
      background-size: 48px 48px;
    }
  </style>
</head>

<body class="bg-[#070A12] text-white antialiased">
  <!-- Top bar -->
  <header class="sticky top-0 z-50 border-b border-white/10 bg-[#070A12]/70 backdrop-blur">
    <div class="mx-auto max-w-6xl px-4 py-3 flex items-center justify-between">
      <a href="#" class="flex items-center gap-2">
        <span class="inline-flex h-8 w-8 items-center justify-center rounded-xl bg-white/10 ring-1 ring-white/10">
          <!-- simple icon -->
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none">
            <path d="M10 18a8 8 0 1 1 5.3-14l4.7 4.7" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
            <path d="M21 21l-4.2-4.2" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
            <path d="M9 11h6" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
            <path d="M12 8v6" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
          </svg>
        </span>
        <span class="font-semibold tracking-tight">Sherlock TG</span>
      </a>

      <nav class="hidden md:flex items-center gap-6 text-sm text-white/70">
        <a href="#features" class="hover:text-white">Возможности</a>
        <a href="#flow" class="hover:text-white">Как работает</a>
        <a href="#faq" class="hover:text-white">FAQ</a>
        <a href="#ethics" class="hover:text-white">Законность</a>
      </nav>

      <div class="flex items-center gap-2">
        <!-- TODO: замени ссылку на своего бота -->
        <a href="https://t.me/your_bot" class="rounded-xl bg-white text-black px-4 py-2 text-sm font-medium hover:bg-white/90">
          Открыть в Telegram
        </a>
      </div>
    </div>
  </header>

  <!-- Hero -->
  <section class="relative overflow-hidden">
    <div class="absolute inset-0 gridlines opacity-40"></div>
    <div class="absolute -top-40 left-1/2 h-[520px] w-[520px] -translate-x-1/2 rounded-full bg-gradient-to-b from-cyan-500/25 to-fuchsia-500/0 blur-3xl"></div>

    <div class="relative noise mx-auto max-w-6xl px-4 pt-14 pb-16">
      <div class="grid gap-10 md:grid-cols-2 md:items-center">
        <div>
          <p class="inline-flex items-center gap-2 rounded-full border border-white/10 bg-white/5 px-3 py-1 text-xs text-white/70">
            <span class="h-1.5 w-1.5 rounded-full bg-cyan-400"></span>
            OSINT-аудит • риск-индикаторы • структурированные отчёты
          </p>

          <h1 class="mt-4 text-4xl md:text-5xl font-semibold leading-tight">
            Проверяй цифровой след — <span class="text-white/70">быстро, аккуратно, законно</span>
          </h1>

          <p class="mt-4 text-white/70 leading-relaxed">
            Sherlock TG помогает собрать сигналы из открытых источников, привести их к понятному виду
            и выдать отчёт с рекомендациями по цифровой гигиене. Без “шума”, без лишней драматизации —
            только то, что полезно для безопасности.
          </p>

          <div class="mt-7 flex flex-col sm:flex-row gap-3">
            <a href="https://t.me/your_bot" class="rounded-2xl bg-white text-black px-5 py-3 text-sm font-semibold hover:bg-white/90">
              Запустить бота
            </a>
            <a href="#ethics" class="rounded-2xl border border-white/15 bg-white/5 px-5 py-3 text-sm font-semibold text-white hover:bg-white/10">
              Принципы и ограничения
            </a>
          </div>

          <div class="mt-8 grid grid-cols-3 gap-3 text-xs text-white/60">
            <div class="rounded-2xl border border-white/10 bg-white/5 p-3">
              <div class="text-white font-semibold">Сводка</div>
              <div class="mt-1">коротко и по делу</div>
            </div>
            <div class="rounded-2xl border border-white/10 bg-white/5 p-3">
              <div class="text-white font-semibold">Контекст</div>
              <div class="mt-1">ссылки и источники</div>
            </div>
            <div class="rounded-2xl border border-white/10 bg-white/5 p-3">
              <div class="text-white font-semibold">Рекомендации</div>
              <div class="mt-1">что улучшить</div>
            </div>
          </div>
        </div>

        <!-- Right card -->
        <div class="rounded-3xl border border-white/10 bg-gradient-to-b from-white/8 to-white/3 p-6 shadow-2xl shadow-cyan-500/10">
          <div class="flex items-center justify-between">
            <div>
              <div class="text-sm font-semibold">Пример отчёта</div>
              <div class="text-xs text-white/60 mt-1">формат: карточки + источники + вывод</div>
            </div>
            <span class="rounded-full bg-black/30 px-3 py-1 text-xs text-white/60 border border-white/10">demo</span>
          </div>

          <div class="mt-5 space-y-3">
            <div class="rounded-2xl border border-white/10 bg-black/20 p-4">
              <div class="text-xs text-white/60">Индикаторы</div>
              <div class="mt-2 flex flex-wrap gap-2 text-xs">
                <span class="rounded-full bg-white/10 px-3 py-1 border border-white/10">упоминания</span>
                <span class="rounded-full bg-white/10 px-3 py-1 border border-white/10">пересечения</span>
                <span class="rounded-full bg-white/10 px-3 py-1 border border-white/10">публичные профили</span>
                <span class="rounded-full bg-white/10 px-3 py-1 border border-white/10">риски приватности</span>
              </div>
            </div>

            <div class="rounded-2xl border border-white/10 bg-black/20 p-4">
              <div class="text-xs text-white/60">Структура результата</div>
              <ul class="mt-2 space-y-2 text-sm text-white/80">
                <li class="flex gap-2"><span class="text-cyan-300">•</span>Сводка: что найдено / что не найдено</li>
                <li class="flex gap-2"><span class="text-cyan-300">•</span>Ссылки: где именно это видно</li>
                <li class="flex gap-2"><span class="text-cyan-300">•</span>Рекомендации: что закрыть/усилить</li>
              </ul>
            </div>

            <div class="rounded-2xl border border-white/10 bg-black/20 p-4">
              <div class="text-xs text-white/60">Важно</div>
              <p class="mt-2 text-sm text-white/70">
                Sherlock TG предназначен для аудита собственной информации и задач безопасности.
                Использование для преследования/доксинга запрещено.
              </p>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- Features -->
  <section id="features" class="mx-auto max-w-6xl px-4 py-16">
    <div class="flex items-end justify-between gap-6">
      <div>
        <h2 class="text-3xl font-semibold">Что умеет Sherlock TG</h2>
        <p class="mt-2 text-white/70 max-w-2xl">
          Не “магия”, а аккуратная работа с открытыми источниками: собираем сигналы, нормализуем, показываем контекст.
        </p>
      </div>
      <div class="hidden md:block text-xs text-white/60">
        Принцип: <span class="text-white">меньше шума → больше смысла</span>
      </div>
    </div>

    <div class="mt-10 grid gap-4 md:grid-cols-3">
      <div class="rounded-3xl border border-white/10 bg-white/5 p-6">
        <div class="text-sm font-semibold">Сбор сигналов</div>
        <p class="mt-2 text-sm text-white/70">
          Публичные упоминания, открытые профили и другие доступные следы — с указанием источников.
        </p>
      </div>
      <div class="rounded-3xl border border-white/10 bg-white/5 p-6">
        <div class="text-sm font-semibold">Нормализация</div>
        <p class="mt-2 text-sm text-white/70">
          Убираем повторы, группируем находки, выделяем важное. Результат выглядит как отчёт, а не “простыня”.
        </p>
      </div>
      <div class="rounded-3xl border border-white/10 bg-white/5 p-6">
        <div class="text-sm font-semibold">Риск-подсказки</div>
        <p class="mt-2 text-sm text-white/70">
          Набор индикаторов приватности и практические рекомендации: что исправить, где усилить защиту.
        </p>
      </div>

      <div class="rounded-3xl border border-white/10 bg-white/5 p-6 md:col-span-2">
        <div class="text-sm font-semibold">Отчёты, которыми удобно делиться</div>
        <p class="mt-2 text-sm text-white/70">
          Краткая сводка + блоки доказательств (ссылки/контекст) + выводы. Формат удобен для команды, клиента или личного архива.
        </p>
        <div class="mt-4 flex flex-wrap gap-2 text-xs text-white/70">
          <span class="rounded-full border border-white/10 bg-white/5 px-3 py-1">сводка</span>
          <span class="rounded-full border border-white/10 bg-white/5 px-3 py-1">контекст</span>
          <span class="rounded-full border border-white/10 bg-white/5 px-3 py-1">рекомендации</span>
          <span class="rounded-full border border-white/10 bg-white/5 px-3 py-1">честные “не найдено”</span>
        </div>
      </div>

      <div class="rounded-3xl border border-white/10 bg-white/5 p-6">
        <div class="text-sm font-semibold">Приватность по умолчанию</div>
        <p class="mt-2 text-sm text-white/70">
          Минимизируем хранение, даём контроль над историей и объясняем ограничения результата.
        </p>
      </div>
    </div>
  </section>

  <!-- Flow -->
  <section id="flow" class="mx-auto max-w-6xl px-4 pb-16">
    <div class="rounded-[32px] border border-white/10 bg-gradient-to-b from-white/6 to-white/3 p-8">
      <h2 class="text-2xl font-semibold">Как это устроено</h2>
      <p class="mt-2 text-white/70 max-w-3xl">
        Вся логика построена вокруг “запрос → проверка → группировка → отчёт”.
        Мы стараемся показывать проверяемый контекст и не обещать невозможного.
      </p>

      <div class="mt-8 grid gap-4 md:grid-cols-4">
        <div class="rounded-2xl border border-white/10 bg-black/20 p-5">
          <div class="text-xs text-white/60">Шаг 1</div>
          <div class="mt-2 font-semibold">Запрос</div>
          <div class="mt-2 text-sm text-white/70">Выбираешь тип проверки и вводишь данные, которые имеешь право проверять.</div>
        </div>
        <div class="rounded-2xl border border-white/10 bg-black/20 p-5">
          <div class="text-xs text-white/60">Шаг 2</div>
          <div class="mt-2 font-semibold">Сбор</div>
          <div class="mt-2 text-sm text-white/70">Собираем сигналы из открытых источников и фиксируем ссылки.</div>
        </div>
        <div class="rounded-2xl border border-white/10 bg-black/20 p-5">
          <div class="text-xs text-white/60">Шаг 3</div>
          <div class="mt-2 font-semibold">Смысл</div>
          <div class="mt-2 text-sm text-white/70">Упорядочиваем: группы, пересечения, повторы, приоритет.</div>
        </div>
        <div class="rounded-2xl border border-white/10 bg-black/20 p-5">
          <div class="text-xs text-white/60">Шаг 4</div>
          <div class="mt-2 font-semibold">Отчёт</div>
          <div class="mt-2 text-sm text-white/70">Сводка + доказательства + рекомендации по защите.</div>
        </div>
      </div>
    </div>
  </section>

  <!-- Ethics -->
  <section id="ethics" class="mx-auto max-w-6xl px-4 pb-16">
    <div class="grid gap-6 md:grid-cols-2">
      <div class="rounded-3xl border border-white/10 bg-white/5 p-7">
        <h2 class="text-2xl font-semibold">Законность и ответственность</h2>
        <p class="mt-3 text-white/70 leading-relaxed">
          Sherlock TG создан для задач цифровой безопасности: проверки <b>собственных</b> данных,
          аудита публичных следов компании/бренда и работы при наличии правовых оснований или согласия.
        </p>
        <ul class="mt-5 space-y-2 text-sm text-white/75">
          <li class="flex gap-2"><span class="text-emerald-300">✓</span>проверка собственного цифрового следа</li>
          <li class="flex gap-2"><span class="text-emerald-300">✓</span>мониторинг публичных упоминаний бренда</li>
          <li class="flex gap-2"><span class="text-emerald-300">✓</span>безопасность аккаунтов и рекомендации</li>
          <li class="flex gap-2"><span class="text-rose-300">✕</span>доксинг, преследование, незаконный сбор/распространение персональных данных</li>
        </ul>
      </div>

      <div class="rounded-3xl border border-white/10 bg-white/5 p-7">
        <h3 class="text-lg font-semibold">Честные ограничения</h3>
        <p class="mt-3 text-white/70 leading-relaxed">
          Открытые источники могут быть неполными или содержать ошибки.
          Мы показываем “найдено / не найдено” и стараемся давать проверяемые ссылки, а не догадки.
        </p>
        <div class="mt-5 rounded-2xl border border-white/10 bg-black/20 p-5 text-sm text-white/70">
          Совет: используйте результаты как <b>повод перепроверить</b>, а не как окончательный вердикт.
        </div>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section id="faq" class="mx-auto max-w-6xl px-4 pb-20">
    <div class="flex items-end justify-between gap-6">
      <div>
        <h2 class="text-3xl font-semibold">FAQ</h2>
        <p class="mt-2 text-white/70">Короткие ответы на частые вопросы.</p>
      </div>
      <a href="https://t.me/your_bot" class="hidden md:inline-flex rounded-2xl border border-white/15 bg-white/5 px-5 py-3 text-sm font-semibold hover:bg-white/10">
        Перейти в Telegram
      </a>
    </div>

    <div class="mt-10 grid gap-4 md:grid-cols-2">
      <details class="rounded-3xl border border-white/10 bg-white/5 p-6">
        <summary class="cursor-pointer font-semibold">Это легально?</summary>
        <p class="mt-3 text-sm text-white/70">
          Инструмент рассчитан на анализ <b>открытых</b> данных и задачи безопасности. Ответственность за законность использования
          несёт пользователь. Мы прямо запрещаем применение для доксинга/преследования.
        </p>
      </details>

      <details class="rounded-3xl border border-white/10 bg-white/5 p-6">
        <summary class="cursor-pointer font-semibold">Почему иногда “ничего не найдено”?</summary>
        <p class="mt-3 text-sm text-white/70">
          Потому что в открытых источниках может не быть сигналов, либо они скрыты настройками приватности,
          либо данные не совпали. “Не найдено” — тоже результат.
        </p>
      </details>

      <details class="rounded-3xl border border-white/10 bg-white/5 p-6">
        <summary class="cursor-pointer font-semibold">Вы храните мои запросы?</summary>
        <p class="mt-3 text-sm text-white/70">
          Политику хранения лучше описать честно под вашу реализацию. Если хранения нет — так и напишите.
          Если есть — укажите сроки и способ удаления истории.
        </p>
      </details>

      <details class="rounded-3xl border border-white/10 bg-white/5 p-6">
        <summary class="cursor-pointer font-semibold">Можно ли получить отчёт в файл?</summary>
        <p class="mt-3 text-sm text-white/70">
          Можно добавить экспорт (PDF/HTML/заметка). На лендинге можно оставить как “в разработке” или включить, если уже готово.
        </p>
      </details>
    </div>

    <div class="mt-10 rounded-[32px] border border-white/10 bg-gradient-to-r from-white/7 to-white/3 p-8 flex flex-col md:flex-row md:items-center md:justify-between gap-6">
      <div>
        <div class="text-xl font-semibold">Готов начать аудит своего цифрового следа?</div>
        <div class="mt-2 text-white/70">Запусти Sherlock TG в Telegram и получи структурированный результат.</div>
      </div>
      <a href="https://t.me/your_bot" class="rounded-2xl bg-white text-black px-6 py-3 text-sm font-semibold hover:bg-white/90 text-center">
        Запустить Sherlock TG
      </a>
    </div>
  </section>

  <footer class="border-t border-white/10">
    <div class="mx-auto max-w-6xl px-4 py-10 flex flex-col md:flex-row md:items-center md:justify-between gap-4 text-sm text-white/60">
      <div class="flex items-center gap-2">
        <span class="inline-flex h-7 w-7 items-center justify-center rounded-xl bg-white/10 ring-1 ring-white/10">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none">
            <path d="M10 18a8 8 0 1 1 5.3-14l4.7 4.7" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
            <path d="M21 21l-4.2-4.2" stroke="currentColor" stroke-width="1.8" stroke-linecap="round"/>
          </svg>
        </span>
        <span>© <span id="y"></span> Sherlock TG</span>
      </div>

      <div class="flex flex-wrap gap-4">
        <a class="hover:text-white" href="#ethics">Законность</a>
        <a class="hover:text-white" href="#faq">FAQ</a>
        <!-- TODO: добавь свои страницы -->
        <a class="hover:text-white" href="#" onclick="alert('Добавь ссылку на политику конфиденциальности'); return false;">Политика</a>
        <a class="hover:text-white" href="#" onclick="alert('Добавь контакт/поддержку'); return false;">Поддержка</a>
      </div>
    </div>
  </footer>

  <script>
    document.getElementById('y').textContent = new Date().getFullYear();
  </script>
</body>
</html>
