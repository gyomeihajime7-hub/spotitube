# Telegram File Management Bot

A premium Telegram bot for file management with PostgreSQL storage, supporting files up to 2GB.

## Features

- 📁 Upload any file type up to 2GB
- 💾 Store file metadata in PostgreSQL database
- 📱 Premium UI with interactive buttons
- 🔄 Download files with smart type detection
- 🚀 Ready for Render Web Service deployment

## Quick Start

### For Render Deployment

1. Fork this repository
2. Connect your Render account to GitHub
3. Create a new Web Service from this repository
4. Set environment variables:
   - `BOT_TOKEN`: Your Telegram bot token from @BotFather
   - `DATABASE_URL`: Your PostgreSQL database connection string

### Environment Variables

```bash
BOT_TOKEN=your_telegram_bot_token
DATABASE_URL=postgresql://user:password@host:port/database
FLASK_SECRET_KEY=your_secret_key_for_sessions
```

## Commands

- `/start` - Welcome message and bot introduction
- `/myfiles` - View and download your uploaded files
- `/help` - Detailed usage instructions

## File Support

- **Documents**: PDF, DOCX, TXT, ZIP, etc.
- **Images**: JPG, PNG, GIF, WebP
- **Videos**: MP4, AVI, MOV, WebM
- **Audio**: MP3, WAV, OGG, M4A
- **Voice Notes**: Telegram voice messages
- **Video Notes**: Telegram video messages

## Architecture

- **Backend**: Flask web application with health endpoints
- **Database**: PostgreSQL with SQLAlchemy ORM
- **Bot Framework**: python-telegram-bot with async support
- **Deployment**: Optimized for Render Web Service

## File Structure

```
├── main.py              # Flask app and bot initialization
├── bot_handlers.py      # Telegram bot command handlers
├── models.py           # Database models and schema
├── Procfile           # Render deployment configuration
├── render.yaml        # Render service configuration
├── pyproject.toml     # Python dependencies
└── .env.example       # Environment variables template
```

## Database Schema

The bot uses a single `FileMetadata` table:

- `user_id`: Telegram user ID
- `file_id`: Telegram file ID for downloads
- `filename`: Original filename
- `file_size`: File size in bytes
- `mime_type`: Detected MIME type
- `upload_date`: Timestamp of upload

## Deployment

### Render Web Service

1. Connect this repository to Render
2. Use the provided `render.yaml` configuration
3. Set environment variables in Render dashboard
4. Deploy automatically on git push

### Local Development

```bash
# Install dependencies
pip install -r requirements.txt

# Set environment variables
cp .env.example .env
# Edit .env with your values

# Run the bot
python main.py
```

## License

MIT License - see LICENSE file for details

## Support

For issues or questions, please open a GitHub issue.