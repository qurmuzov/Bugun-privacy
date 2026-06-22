# Bugun — Privacy Policy (GitHub Pages)

Политика конфиденциальности для App Store **без своего домена**.

## 1. Создай репозиторий на GitHub

1. [github.com/new](https://github.com/new)
2. Имя, например: **`bugun-privacy`** (или `BugunIOS`, если заливаешь весь проект)
3. **Public**
4. Create repository

## 2. Залей папку `docs`

### Вариант A — отдельный репозиторий только для политики (проще)

```bash
cd /Users/ayewka/Desktop/BugunIOS/docs
git init
git add .
git commit -m "Add Bugun privacy policy"
git branch -M main
git remote add origin https://github.com/ТВОЙ_USERNAME/bugun-privacy.git
git push -u origin main
```

Потом в настройках репо: **Settings → Pages → Build from branch → main → / (root)**  
(если заливаешь содержимое `docs/` в корень репо, не в подпапку)

### Вариант B — весь проект BugunIOS

```bash
cd /Users/ayewka/Desktop/BugunIOS
git add docs/
git commit -m "Add privacy policy for GitHub Pages"
git push
```

**Settings → Pages → Branch: `main` → Folder: `/docs`**

## 3. Включи GitHub Pages

Repo → **Settings** → **Pages**:
- Source: **Deploy from a branch**
- Branch: **main**
- Folder: **`/docs`** (вариант B) или **`/ (root)`** (вариант A)
- Save

Через 1–3 минуты сайт будет доступен.

## 4. Твоя ссылка для App Store

Подставь свой **USERNAME** и **REPO**:

| Как залил | URL для App Store Connect |
|-----------|---------------------------|
| Репо `bugun-privacy`, файлы в **корне** | `https://USERNAME.github.io/bugun-privacy/privacy/` |
| Репо `BugunIOS`, папка **`docs/`** | `https://USERNAME.github.io/BugunIOS/privacy/` |

**Пример:** пользователь `rasulq`, репо `bugun-privacy`:
```
https://rasulq.github.io/bugun-privacy/privacy/
```

Открой ссылку в браузере — должна открыться политика на AZ/RU/EN.

## 5. App Store Connect

1. [appstoreconnect.apple.com](https://appstoreconnect.apple.com) → **Bugun**
2. **App Information** (или при отправке версии)
3. **Privacy Policy URL** → вставь ссылку из таблицы выше
4. Сохрани

Apple принимает ссылки на **github.io** — это нормально.

## 6. Обнови ссылку в приложении (опционально)

В `Bugun/Services/AppConfig.swift` замени:

```swift
static let privacyPolicyURL = URL(string: "https://USERNAME.github.io/bugun-privacy/privacy/")!
```

Чтобы кнопка «Политика конфиденциальности» в настройках открывала ту же страницу.

## Файлы

- `privacy/index.html` — основная страница (URL `/privacy/`)
- `privacy.html` — дубликат
- `index.html` — главная с ссылкой

Контакт: support@bugun.app
