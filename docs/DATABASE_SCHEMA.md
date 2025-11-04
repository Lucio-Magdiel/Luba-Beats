# 🗄️ Database Schema - Luba Beats

## Tablas Principales

### users

```sql
CREATE TABLE users (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  email VARCHAR(255) UNIQUE NOT NULL,
  username VARCHAR(100) UNIQUE NOT NULL,
  full_name VARCHAR(255),
  bio TEXT,
  avatar_url VARCHAR(500),
  role VARCHAR(20) NOT NULL DEFAULT 'oyente',
  is_active BOOLEAN DEFAULT true,
  is_verified BOOLEAN DEFAULT false,
  created_at TIMESTAMP DEFAULT NOW()
);

tracks SQL

CREATE TABLE tracks (
  id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  user_id UUID NOT NULL REFERENCES users(id) ON DELETE CASCADE,
  title VARCHAR(255) NOT NULL,
  description TEXT,
  type VARCHAR(10) NOT NULL CHECK (type IN ('cancion', 'beat')),
  audio_url VARCHAR(500) NOT NULL,
  cover_url VARCHAR(500),
  price DECIMAL(10, 2),
  is_published BOOLEAN DEFAULT true,
  play_count INTEGER DEFAULT 0,
  like_count INTEGER DEFAULT 0,
  created_at TIMESTAMP DEFAULT NOW()
);
```

## likes, comments, playlists, favorites, followers
## Todas las tablas de relaciones están documentadas en el archivo completo.

Relaciones
1 Usuario → Muchos Tracks
1 Track → Muchos Likes/Comments
1 Playlist → Muchos Tracks
