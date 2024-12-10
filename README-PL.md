# Text Messenger

Aplikacja **Text Messenger** to system do przesyłania wiadomości, który składa się z dwóch głównych komponentów: **klienta** i **serwera**. Aplikacja umożliwia bezpieczną komunikację między użytkownikami w czasie rzeczywistym.

## Wymagania

Uruchomienie za pomocą Dockera:

- **Docker**

Samodzielne uruchomienie:

- Erlang
- Elixir
- PostgreSQL

Samodzielne uruchomienie wymaga skonfigurowania połączenia z bazą PostgreSQL w text-messenger-server/config/dev.exs, w miejscu ```config :text_messenger_server, TextMessengerServer.Repo```.

## Instalacja

### 1. Klonowanie repozytorium z submodułami

Aby sklonować repozytorium i wszystkie submoduły, użyj poniższego polecenia:
```
git clone --recurse-submodules https://github.com/kperdek8/text-messenger.git
cd text-messenger
```

### 2a. Uruchomienie aplikacji za pomocą Docker Compose

Po sklonowaniu repozytorium, uruchom aplikację za pomocą Docker Compose:
```
docker-compose up --build
```

### 2b. Uruchomienie aplikacji za pomocą mix (Elixir)

Po sklonowaniu wejdź do folderu text-messenger-server, pobierz zależności, utwórz bazę danych, przeprowadź migrację danych oraz uruchom serwer:
```
cd text-messenger-server
mix deps.get
mix ecto.create
mix ecto.migrate
mix phx.server
```

Następnie przejdź do folderu klienta, pobierz zależności i go uruchom:
```
cd ..
cd text-messenger-client
mix deps.get
mix phx.server
```

### 3. Dostęp do aplikacji

- **Frontend (Client)**: http://localhost:4000
- **Backend (Server)**: http://localhost:4001
