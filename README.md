# RiftShield VPN 🛡️

A professional, enterprise-grade VPN application built with Flutter for Android and Windows platforms.

## 🚀 Features

- **Multi-Protocol Support**: OpenVPN, WireGuard, IKEv2, L2TP/IPSec
- **Cross-Platform**: Android and Windows support
- **Enterprise Security**: AES-256 encryption, kill switch, DNS leak protection
- **Smart Server Selection**: Automatic best server selection based on ping and load
- **Modern UI**: Material 3 design with dark/light theme support
- **Real-time Monitoring**: Connection status, speed tests, data usage tracking

## 🏗️ Architecture

This project follows **Clean Architecture** principles with feature-based modular structure.

### 📁 Project Structure

```
lib/
├── config/             # App configuration & routing
├── core/              # Core utilities, theme, constants
├── data/              # Data layer (models, repositories, data sources)
├── domain/            # Domain layer (entities, repositories, use cases)
├── features/          # Feature-based modules
│   ├── vpn_connection/    # VPN connection feature
│   ├── server_management/ # Server management feature
│   ├── user_management/   # User management feature
│   └── settings/          # Settings feature
├── platform/          # Platform-specific implementations
│   ├── android/           # Android VPN implementation
│   ├── windows/           # Windows VPN implementation
│   └── common/            # Common platform interfaces
├── presentation/      # UI layer (pages, widgets, BLoCs)
└── services/          # Business logic services
```

## 🛠️ Technology Stack

- **Flutter**: Cross-platform UI framework
- **BLoC**: State management pattern
- **Dio**: HTTP client for API calls
- **Hive**: Local database
- **Get It**: Dependency injection
- **Go Router**: Navigation management

## 📱 Platform Support

### Android
- **Minimum SDK**: API 21 (Android 5.0)
- **VPN Service**: Android VpnService API
- **Permissions**: VPN, network access, location
- **Features**: Quick Settings tile, auto-connect, always-on VPN

### Windows
- **Minimum Version**: Windows 10
- **VPN Implementation**: Native Windows VPN APIs
- **Features**: System tray integration, startup support

## 🚀 Getting Started

### Prerequisites
```bash
Flutter SDK 3.8.1+
Dart SDK 3.8.1+
Android Studio / VS Code
```

### Installation

1. **Install dependencies**
   ```bash
   flutter pub get
   ```

2. **Run the app**
   ```bash
   # For Android
   flutter run

   # For Windows  
   flutter run -d windows
   ```

### Configuration

Update `assets/config/app_config.json` with your VPN server settings:

```json
{
  "api_base_url": "https://your-api-server.com",
  "vpn_api_key": "your_api_key",
  "is_debug_mode": true,
  "connection_timeout": 30000
}
```

## 📊 Key Components

### VPN Service
- **Android**: `RiftShieldVpnService` - Native Android VPN service
- **Windows**: `VpnServiceWindows` - Windows VPN implementation
- **Common**: `VpnPlatformInterface` - Abstract platform interface

### State Management
- **VPN BLoC**: Manages VPN connection state
- **Server BLoC**: Handles server selection and management
- **User BLoC**: Manages user authentication and profile

### Security Features
- **Kill Switch**: Network blocking on VPN failure
- **DNS Leak Protection**: Secure DNS routing
- **Auto-Connect**: Automatic connection on untrusted networks

## 🔧 Development

### Code Generation
```bash
flutter packages pub run build_runner build
```

### Testing
```bash
flutter test
```

### Build for Production

#### Android
```bash
flutter build apk --release
```

#### Windows
```bash
flutter build windows --release
```

## 📝 Next Steps

1. **Install Dependencies**: Run `flutter pub get`
2. **Configure API**: Update config files with your VPN servers
3. **Implement VPN Logic**: Complete platform-specific VPN implementations
4. **Add Server API**: Integrate with your VPN server infrastructure
5. **Test on Device**: Test with real VPN permissions on Android
6. **UI Enhancement**: Customize the user interface
7. **Security Testing**: Perform security audits and penetration testing

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License.

## 🔒 Security Notice

This is a template VPN application. For production use:
- Implement proper VPN protocols (OpenVPN/WireGuard)
- Set up secure server infrastructure
- Perform security audits
- Implement certificate pinning
- Add proper logging and monitoring

---

**RiftShield VPN** - Professional Privacy Protection 🛡️
