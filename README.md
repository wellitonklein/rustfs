# Projeto RustFS

Este projeto é composto por duas partes principais: `backend` e `frontend`. Abaixo estão as instruções para build e execução de cada uma dessas partes.

## Banco de Dados

### Descrição

O Banco de Dados será Postgres, um banco de dados relacional. Usaremos o Docker para executar o Postgres em um contêiner e não usaremos nenhum ORM para manter as coisas simples. Iremos interagir com o banco de dados usando consultas SQL escritas diretamente nos manipuladores Rocket.

- Postgres - Banco de Dados Relacional
- Docker - Dockerfile e Docker Compose para executar Postgres

### Comandos

#### Executar o Container

Para executar o container do PostgreSQL, utilize o comando:

```sh
docker compose up -d
```

#### Acessar o Container

Para acessar o container do PostgreSQL, utilize o comando:

```sh
docker exec -it db psql -U postgres
```

## Backend

### Descrição

O Backend será construído usando Rocket, um framework web para Rust. Rocket foi projetado para maximizar a experiência do desenvolvedor. Usaremos o Rocket para construir uma API REST simples que irá interagir com o banco de dados.

- Rust – linguagem de programação central
- Rocket - Rust Framework para construção de servidores web

### Comandos

#### Build

Para buildar o backend, execute o seguinte comando:

```sh
cd backend
cargo build --release
```

#### Executar

Para executar o backend, utilize o comando:

```sh
cargo run
```

## Frontend

### Descrição

O front-end será construído usando Yew, uma nova estrutura Rust para construir aplicativos web clientes. Yew é inspirado em Elm e React e foi projetado para ser simples e fácil de usar. Usaremos Trunk para servir o frontend e Tailwind CSS para estilização. Tudo isso será compilado em Web Assembly e executado no navegador.

- Rust – linguagem de programação central
- Web Assembly - Para executar Rust no navegador
- Yew - Rust Framework para construir aplicativos web clientes
- Tailwind CSS – Para estilizar o frontend

### Comandos

#### Pré-requisitos

Para preparar o ambiente para usar WASM + Trunk

```sh
rustup target add wasm32-unknown-unknown && cargo install trunk && trunk --version
```

#### Build

Para buildar o frontend, execute o seguinte comando:

```sh
cd frontend
cargo build --target wasm32-unknown-unknown
```

#### Executar

Para executar o frontend, utilize o comando:

```sh
trunk serve
```
