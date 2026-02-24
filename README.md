Над нашим репозиторием пыхтели наши ребята:

1 Код - Карты:


2 Код - Player, item:



3 Код - Кланы:

CREATE TABLE IF NOT EXISTS clans (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    tag TEXT UNIQUE,
    description TEXT,
    trophies INTEGER DEFAULT 0,
    required_trophies INTEGER DEFAULT 0,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE IF NOT EXISTS clan_members (
    player_id INTEGER NOT NULL,
    clan_id INTEGER NOT NULL,
    role TEXT DEFAULT 'member',  
    join_date DATETIME DEFAULT CURRENT_TIMESTAMP,
);

CREATE TABLE IF NOT EXISTS clan_events (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    clan_id INTEGER NOT NULL,
    event_type TEXT NOT NULL,    
    description TEXT,
    event_time DATETIME DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY(clan_id) REFERENCES clans(id) ON DELETE CASCADE
);

CREATE TABLE IF NOT EXISTS clan_wars (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    clan_id INTEGER NOT NULL,
    season INTEGER NOT NULL,
    score INTEGER DEFAULT 0,
    start_date DATETIME,
    end_date DATETIME,
    FOREIGN KEY(clan_id) REFERENCES clans(id) ON DELETE CASCADE
);


один из примеров:
|Обычный|||||
