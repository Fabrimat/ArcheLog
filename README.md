# ArcheLog
ArcheLog is a new data logging and anti-grief software.

ArcheLog is still in development, it'll ready when it is ready.

Roadmap:
- [ ] This README
- [ ] Base plugin
- [ ] Commands
- [ ] Permissions
- [ ] Config
- [ ] Update checker
- [ ] Metrics
- [ ] Error control
- [ ] APIs
- [ ] Standalone tool
- [ ] Database
  - [ ] SQLite
  - [ ] H2
    - [ ] Database compression
  - [ ] MySQL (InnoDB)
    - [ ] Compression protocol
    - [ ] Table compression
    - [ ] Table partitioning
  - [ ] Database migration
- [ ] Logging
  - [ ] Blocks
    - [ ] Normal blocks
    - [ ] Signs
    - [ ] Containers
    - [ ] Nether portals
  - [ ] Entities
    - [ ] Living entities
    - [ ] Non living entities
      - [ ] Armorstand
      - [ ] Item frame
      - [ ] Painting
    - [ ] Despawn types
      - [ ] Die
      - [ ] Kill
      - [ ] Despawn (Paper only)
  - [ ] Player commands
  - [ ] Chat
- [ ] Lookup
  - [ ] Blocks
  - [ ] Entities
  - [ ] Player commands
  - [ ] Chat
- [ ] Rollback
  - [ ] Blocks
    - [ ] Normal blocks
    - [ ] Signs
    - [ ] Containers
  - [ ] Entities
    - [ ] Living entities (how?)
    - [ ] Non living entities
      - [ ] Armorstand
      - [ ] Item frame
      - [ ] Painting
- [ ] Restore
  - [ ] Blocks
    - [ ] Normal blocks
    - [ ] Signs
    - [ ] Containers
  - [ ] Entities
    - [ ] Living entities (how?)
    - [ ] Non living entities
      - [ ] Armorstand
      - [ ] Item frame
      - [ ] Painting
- [ ] Purge
- [ ] Undo
- [ ] WorldEdit integration
  - [ ] Block logging
  - [ ] Selection
- [ ] Multi version support
  - [ ] 1.8 - 1.12
  - [ ] 1.13+ (Flattening)
  
Database structure:
- Block simple
  - id [pk] (int)
  - x (int)
  - y (int)
  - z (int)
- Block advanced
  - id [pk] (int)
  - x (double)
  - y (double)
  - z (double)
- Block modify
  - id [pk] (int)
  - playerid [fk] (int)
  - blocksimpleid [fk] (int)
  - time (timestamp)
  - block_id (int)
  - block_name (string)
  - data (string ?)
  - rolled_back (bool)
- Container snapshot
  - id [pk] (int)
  - blockmodid [fk] (int)
  - data (string ?)
- Container transaction
  - id [pk] (int)
  - blocksimpleid [fk] (int)
  - playerid [fk] (int)
  - time (timestamp)
  - data (string ?)
  - rolled_back (bool)
- Player
  - id [pk] (int)
  - uuid (string)
- Player names
  - id [pk] (int)
  - playerid [fk] (int)
  - name (string)
- Entity death
  - id [pk] (int)
  - playerid [fk] (int)
  - blockadvancedid [fk] (int)
  - playerid [fk] (int)
  - type (string)
  - data (string ?)
  - rolled_back (bool)
- Player chat
  - id [pk] (int)
  - playerid [fk] (int)
  - time (timestamp)
  - message (string)
- Player command
  - id [pk] (int)
  - playerid [fk] (int)
  - time (timestamp)
  - command (string)
