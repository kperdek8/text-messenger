# Text Messenger

**Text Messenger** is a messaging system consisting of two main components: **client** and **server**. The application allows secure communication between users in real time.

## Requirements

Running with Docker:

- **Docker**

Standalone setup:

- **Erlang**
- **Elixir**
- **PostgreSQL**

Standalone setup requires configuring the PostgreSQL connection in `text-messenger-server/config/dev.exs` in the following section:
```
config :text_messenger_server, TextMessengerServer.Repo
```

## Installation

### 1. Cloning the repository with submodules

To clone the repository and all submodules, use the following command:
```
git clone --recurse-submodules https://github.com/kperdek8/text-messenger.git
cd text-messenger
```

### 2a. Running the app with Docker Compose

After cloning the repository, run the application using Docker Compose:
```
docker-compose up --build
```

### 2b. Running the app with mix (Elixir)

After cloning, go to the `text-messenger-server` folder, fetch dependencies, create the database, run migrations, and start the server:
```
cd text-messenger-server
mix deps.get
mix ecto.create
mix ecto.migrate
mix phx.server
```

Then go to the client folder, fetch dependencies, and start the client:
```
cd ..
cd text-messenger-client
mix deps.get
mix phx.server
```

### 3. Accessing the application

- **Frontend (Client)**: http://localhost:4000
- **Backend (Server)**: http://localhost:4001
