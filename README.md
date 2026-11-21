
# Claude Launcher

**Современный кроссплатформенный лаунчер Minecraft на Electron + React.**
Тёмная тема, оранжевый акцент, скруглённый интерфейс и плавные анимации.

`Electron` · `React` · `TypeScript` · `Vite` · `Tailwind CSS` · `Framer Motion`

## Возможности

- **Запуск игры** — Release, Snapshot, Old Beta и Old Alpha по официальному манифесту Mojang (`version_manifest_v2.json`), проверка SHA1 файлов, прогресс с процентами и скоростью загрузки.
- **Загрузчики** — Vanilla, Fabric, Quilt, Forge и NeoForge (устанавливаются автоматически).
- **Аккаунты** — Offline (с offline-UUID), Microsoft (OAuth → Xbox Live → XSTS → Minecraft Services), Ely.by, Littleskin и любой сервер authlib-injector. Токены шифруются через системное хранилище (Electron `safeStorage`).
- **Свой скин** — загрузка PNG в профиль Microsoft, локальное 2D-превью для остальных типов аккаунтов.
- **Сборки (Instances)** — отдельная папка, версия и загрузчик для каждой сборки; клонирование, удаление, иконки.
- **Моды и ресурспаки** — поиск и установка через [Modrinth](https://modrinth.com) с проверкой SHA1.
- **Java** — поиск установленной, автоскачивание Eclipse Temurin 8 / 17 / 21, ручной путь, слайдер памяти, JVM-аргументы (пресет Aikar).
- **Консоль** — живой лог игры с подсветкой и копированием.
- **Новости** — патчноуты Minecraft.
- **Настройки** — язык RU / EN, четыре акцентных цвета, масштаб интерфейса, отключение анимаций, закрытие лаунчера при запуске.
- **Интерфейс** — безрамочное окно, жидкий индикатор вкладок, ripple-эффект, скелетоны загрузки, тосты.

## Вход через Microsoft

Лаунчер использует библиотеку [msmc](https://github.com/Hanro50/MSMC) со встроенным client id, поэтому для начала настройка не нужна. Чтобы использовать **собственное** приложение Azure:

1. [Azure Portal](https://portal.azure.com) → **App registrations** → **New registration**.
2. Тип аккаунтов: **Personal Microsoft accounts** (или Any tenant + personal).
3. Redirect URI: платформа **Mobile and desktop**, значение `http://localhost`.
4. Скопируйте **Application (client) ID** и передайте его в `new Auth({ client_id, redirect })` в `src/main/main.ts`.
5. Для работы с Minecraft Services приложению может потребоваться одобрение Mojang — см. [документацию](https://aka.ms/AppRegInfo).

## Благодарности

[minecraft-launcher-core](https://github.com/Pierce01/MinecraftLauncher-core) · [msmc](https://github.com/Hanro50/MSMC) · [Modrinth](https://modrinth.com) · [Fabric](https://fabricmc.net) · [Quilt](https://quiltmc.org) · [Forge](https://minecraftforge.net) · [NeoForge](https://neoforged.net) · [Eclipse Temurin](https://adoptium.net) · [authlib-injector](https://github.com/yushijinhun/authlib-injector) · [Lucide](https://lucide.dev)

## Лицензия

Укажите лицензию перед публикацией (например, MIT) и добавьте файл `LICENSE`.
