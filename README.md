# PRO-C211 IP Messenger

A Python socket-based LAN messenger with a Tkinter GUI client and a companion FTP file-sharing service for exchanging messages and files between connected peers.

## Features

- TCP chat server (127.0.0.1:8010) managing a registry of connected clients per nickname
- Peer-to-peer connect / disconnect protocol (`connect <name>`, `disconnect <name>`)
- `show list` command to list all online clients with their availability status
- Tkinter GUI client: active-user listbox, chat window, refresh, connect/disconnect buttons
- File sharing via a bundled FTP server (pyftpdlib) — clients upload attachments with `Attach & Send`
- Concurrent per-client threads on both server and client

## Tech Stack

- Python 3 (standard library)
- Tkinter GUI
- `socket` / `threading` networking
- `pyftpdlib` FTP server

## Project Structure

```text
PRO-C211-Student-BoilerplateCode-main/
├── server.py    # Chat + FTP server (setup and ftp threads)
└── client.py    # Tkinter messenger client
```

## Installation

```bash
pip install pyftpdlib
```

## Usage

Start the server:

```bash
python3 server.py
```

Then start one or more clients:

```bash
python3 client.py
```

Enter a nickname and click **Connect to Chat Server**. Use **Refresh** to list users, select one and click **Connect** to start chatting, or **Attach & Send** to upload a file over the built-in FTP share.
