# Soz Alem 🎵

A cross-platform audio card application built with **Flutter** (frontend) and **Django REST Framework** (backend). Users can browse sound cards organized by categories and play audio files directly from the app.

## 📱 Features

- **Sound Cards**: Browse and play audio cards organized by categories
- **Audio Queue**: Add multiple sounds to a queue and play them sequentially
- **Category Management**: View and navigate through different sound categories
- **Customization**: Change colors, edit sound buttons, and personalize the app
- **Dark/Light Theme**: Switch between dark and light mode
- **Cross-Platform**: Runs on Android, iOS, Web, Linux, macOS, and Windows
- **REST API**: Full-featured Django backend with Swagger documentation

## 🛠️ Tech Stack

### Frontend (Flutter)
- **Flutter SDK** ^3.6.0
- **Provider** - State management
- **Dio** - HTTP client for API calls
- **AudioPlayers** - Audio playback
- **Cached Network Image** - Image caching
- **Image Picker & File Picker** - Media selection
- **Flutter ColorPicker** - Color customization
- **Shared Preferences** - Local storage

### Backend (Django)
- **Django** 4.2.x
- **Django REST Framework** - API development
- **drf-yasg** - Swagger/OpenAPI documentation
- **django-cors-headers** - CORS support
- **Pillow** - Image processing
- **SQLite** - Database (default)

## 📁 Project Structure

```
soz_alem/
├── lib/                          # Flutter source code
│   ├── main.dart                 # App entry point
│   ├── data/                     # Static data/mappings
│   ├── models/                   # Data models
│   │   ├── category_model.dart
│   │   ├── sound_button.dart
│   │   └── ...
│   ├── providers/                # State management
│   │   ├── queue_provider.dart   # Audio queue state
│   │   └── settings_provider.dart
│   ├── screens/                  # UI screens
│   │   ├── home_screen.dart
│   │   ├── category_screen.dart
│   │   ├── settings_screen.dart
│   │   └── ...
│   ├── services/                 # API services
│   │   └── api_service.dart
│   └── widgets/                  # Reusable widgets
│       ├── sound_button.dart
│       └── custom_sound_card.dart
├── backend/                      # Django backend
│   ├── manage.py
│   ├── db.sqlite3
│   ├── requirments.txt
│   ├── backend/                  # Django project settings
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── wsgi.py
│   ├── myapp/                    # Main Django app
│   │   ├── models.py             # Category & Card models
│   │   ├── views.py              # API ViewSets
│   │   ├── serializers.py
│   │   └── urls.py
│   └── media/                    # Uploaded files
│       ├── audio/
│       └── images/
├── assets/                       # Static assets
│   ├── icon/
│   ├── png/                      # Category images
│   └── license/
└── android/, ios/, web/, ...     # Platform-specific code
```

## 🚀 Getting Started

### Prerequisites

- **Flutter SDK** 3.6.0 or higher
- **Python** 3.10+
- **pip** (Python package manager)

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirments.txt
   ```

4. Run migrations:
   ```bash
   python manage.py migrate
   ```

5. Create a superuser (optional, for admin access):
   ```bash
   python manage.py createsuperuser
   ```

6. Start the development server:
   ```bash
   python manage.py runserver 0.0.0.0:8000
   ```

The API will be available at `http://127.0.0.1:8000/`

### Frontend Setup

1. From the project root, install Flutter dependencies:
   ```bash
   flutter pub get
   ```

2. Run the app:
   ```bash
   flutter run
   ```

### API Configuration

The Flutter app connects to the backend at `http://10.0.2.2:8000/` (Android emulator localhost). Update the base URL in `lib/services/api_service.dart` for different environments:

- **Android Emulator**: `http://10.0.2.2:8000/`
- **iOS Simulator**: `http://localhost:8000/`
- **Physical Device**: Use your machine's local IP address

## 📡 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/categories/` | GET, POST | List/Create categories |
| `/api/categories/{id}/` | GET, PUT, DELETE | Retrieve/Update/Delete category |
| `/api/cards/` | GET, POST | List/Create sound cards |
| `/api/cards/{id}/` | GET, PUT, DELETE | Retrieve/Update/Delete card |
| `/swagger/` | GET | Swagger UI documentation |
| `/redoc/` | GET | ReDoc documentation |

### Card Model

```json
{
  "id": 1,
  "category": 1,
  "title": "Card Title",
  "image": "/media/cards/images/image.png",
  "audio": "/media/cards/audio/sound.mp3"
}
```

## 🎨 Categories

The app includes predefined categories with custom icons:
- Activities
- Animals
- Clothes
- Emotions
- Food
- Furniture
- Pain
- Places
- Stationery
- Things
- Transport
- And more...

## 📝 License

See the [license](assets/license/) folder for licensing information.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📧 Contact

Project Link: [https://github.com/dench1k1ng/soz_alem](https://github.com/dench1k1ng/soz_alem)

