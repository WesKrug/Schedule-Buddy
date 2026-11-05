# Database Schema for Shuddy (MVP)

## Core Entities

### 1. `users`
- `id`: Primary key
- `name`: String
- `color`: String
- `created_at`: DateTime
- `updated_at`: DateTime

### 2. `groups` (for schedule sharing)
- `id`: Primary key
- `name`: String
- `description`: Text
- `creator_id`: Foreign key to `users.id`
- `created_at`: DateTime
- `updated_at`: DateTime

### 3. `user_groups` (many-to-many relationship)
- `user_id`: Foreign key to `users.id`
- `group_id`: Foreign key to `groups.id`
- `created_at`: DateTime
- `updated_at`: DateTime

### 4. `blocked_times` (for time blocking)
- `id`: Primary key
- `user_id`: Foreign key to `users.id`
- `group_id`: Foreign key to `groups.id`
- `start_time`: DateTime
- `end_time`: DateTime
- `created_at`: DateTime
- `updated_at`: DateTime

## Relationships
- A user can belong to multiple groups (via `user_groups`)
- A group can have many users (via `user_groups`)
- A user can block multiple time slots in a group
- A group can have many blocked time slots

## MVP Considerations
- Use PostgreSQL for relational data
- Add indexes on foreign keys (`user_id`, `group_id`)
- Use Rails' built-in Active Record for ORM
- Authentication via Devise gem
- Authorization via Pundit gem
- Google Calendar integration handled via API calls (not stored in DB)