# Hello! My name is Elegy

![White-haired anime girl standing in sunflower field under blue sky, resembling Ukrainian flag](/resource/elegy.png)

Elegy is a request-response system programmed in natural language. Ukrainian language is currently the target. Elegy is not an artificial intelligence, but she would be happy to assist you.

### Installation
As dependencies Elegy requires:
 - GNU/Linux
 - [CMake](https://cmake.org)
 - [Telegram TDlib](https://core.telegram.org/tdlib/docs/) (Optionally)

Elegy can be build using following instructions:
```
mkdir build
cd build
cmake .. # Optionally -DTd_DIR=${PATH_TO_TELEGRAM_INSTALLATION}
cmake --build .
```

### Usage
```
# Daemon management
elegy_daemon --start                # Start daemon
elegy_daemon --status               # Check daemon status
elegy_daemon --restart              # Restart daemon
elegy_daemon --stop                 # Stop daemon

# Basic command line tool
elegy 'Request text' [ --username <Human-readable user name> ] [ --userid <Unique user identifier> ]

# Telegram bridge (In case Td_DIR was specified)
elegy_telegram_daemon --start       # Start telegram daemon
elegy_telegram_daemon --status      # Check telegram daemon status
elegy_telegram_daemon --restart     # Restart telegram daemon
elegy_telegram_daemon --stop        # Stop telegram daemon
elegy_telegram_daemon --code <CODE> # Pass confirmation code to the daemon
```