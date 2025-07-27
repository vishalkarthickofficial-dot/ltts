# Society App 🏠

A modern Flutter application for society management with Supabase backend integration.

## ✨ Features

### 🔐 Authentication
- Email/password login and signup
- Secure session management with Supabase Auth
- Automatic profile completion flow

### 🏢 User Management
- Complete profile setup with flat selection
- User-specific complaint management
- Profile and logout functionality

### 📝 Complaint Management
- **Modern Submit Form**: Beautiful animated form with validation
- **Smart Categories**: Water, Electricity, Security, Maintenance, Noise, Other
- **Filter by Category**: Interactive filter chips with icons
- **Modern Card Design**: Enhanced complaint cards with status indicators
- **Edit Complaints**: Beautiful modal dialog for editing
- **Delete Confirmation**: Animated confirmation dialog
- **Real-time Updates**: Pull-to-refresh functionality

### 🎨 UI/UX Features
- **Material 3 Design**: Modern design system with custom theming
- **Smooth Animations**: Page transitions, card animations, and micro-interactions
- **Custom Snackbars**: Animated toast notifications with icons and colors
- **Responsive Layout**: Works on various screen sizes
- **SliverAppBar**: Modern scrolling app bar with gradient background
- **Empty States**: Beautiful empty state illustrations

### 🚀 Future-Ready
- **Notices Tab**: Placeholder for society announcements
- [ ] Polls Tab: Placeholder for community voting
- **Admin Role**: Architecture ready for admin functionality
- **Offline Support**: Framework for offline-first features

## 🏗️ Architecture

### Frontend (Flutter)
- **Material 3** design system
- **StatefulWidget** pattern with clean state management
- **Custom widgets** for reusability
- **Supabase Flutter** SDK for backend integration

### Backend (Supabase)
- **PostgreSQL** database with RLS (Row Level Security)
- **Auth** with email/password
- **Real-time** subscriptions (ready for future features)

### Database Schema
```sql
-- Users table
users (
  id UUID PRIMARY KEY REFERENCES auth.users(id),
  name TEXT,
  flat_id INTEGER REFERENCES flats(id),
  created_at TIMESTAMP DEFAULT NOW()
)

-- Flats table (pre-seeded)
flats (
  id SERIAL PRIMARY KEY,
  number TEXT NOT NULL,
  building TEXT,
  created_at TIMESTAMP DEFAULT NOW()
)

-- Complaints table
complaints (
  id SERIAL PRIMARY KEY,
  title TEXT NOT NULL,
  description TEXT NOT NULL,
  category TEXT NOT NULL,
  user_id UUID REFERENCES users(id),
  created_at TIMESTAMP DEFAULT NOW()
)
```

## 🎯 Key Improvements Made

### 1. **Beautiful Edit Complaint Modal**
- Full-screen animated modal with Material 3 design
- Pre-filled form fields with validation
- Smooth enter/exit animations
- Real-time category icon updates

### 2. **Delete Confirmation Dialog**
- Animated warning dialog
- Modern design with proper spacing
- Loading states during deletion
- Confirmation feedback

### 3. **Custom Snackbar System**
- 4 types: Success, Error, Warning, Info
- Animated floating design
- Custom icons and colors
- Auto-dismiss functionality

### 4. **Modern Complaint Cards**
- Category chips with color coding
- Relative date formatting ("Today", "Yesterday", "3 days ago")
- Status indicators
- Hover effects and shadows
- Popup menu integration

### 5. **Enhanced Navigation**
- SliverAppBar with gradient background
- Tab-specific titles
- Profile menu with logout
- Bottom navigation with active/inactive icons

### 6. **Smooth Animations**
- Staggered list item animations
- Form field slide-in effects
- Modal transitions
- Loading state animations

## 🚀 Getting Started

### Prerequisites
- Flutter SDK (3.8.1+)
- Dart SDK
- Android Studio / VS Code
- Supabase account

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd society_app
   ```

2. **Install dependencies**
   ```bash
   flutter pub get
   ```

3. **Configure Supabase**
   - Update `lib/constants.dart` with your Supabase URL and anon key
   - Set up the database schema in your Supabase project

4. **Run the app**
   ```bash
   flutter run
   ```

## 📱 Screenshots

### Complaint Management
- Submit form with modern design
- Filter chips for easy categorization
- Card-based complaint listing
- Edit modal with validation

### Navigation
- Gradient SliverAppBar
- Tab-based navigation
- Profile menu integration

## 🛠️ Development

### Project Structure
```
lib/
├── main.dart                 # App entry point with theme
├── dashboard.dart           # Main navigation structure
├── complaints_tab.dart      # Enhanced complaints management
├── widgets/
│   ├── custom_snackbar.dart        # Toast notifications
│   ├── modern_complaint_card.dart  # Card component
│   ├── edit_complaint_modal.dart   # Edit dialog
│   ├── delete_confirmation_dialog.dart # Delete confirmation
│   └── submit_complaint_form.dart  # Submit form
├── auth_gate.dart          # Authentication logic
├── login_page.dart         # Login/signup interface
├── complete_profile_page.dart # Profile setup
└── constants.dart          # App configuration
```

### Key Dependencies
```yaml
dependencies:
  flutter: sdk
  supabase_flutter: ^1.10.17  # Backend integration
  flutter_hooks: ^0.20.5      # State management helpers
  hooks_riverpod: ^2.5.1      # State management (ready for scaling)
```

### Coding Standards
- Material 3 design patterns
- Responsive design principles
- Clean architecture
- Widget composition over inheritance
- Proper error handling with user feedback

## 🔮 Roadmap

### Phase 2: Notices & Announcements
- [ ] Admin notice creation
- [ ] Notice categories and priorities
- [ ] Push notifications
- [ ] Notice read status

### Phase 3: Polls & Voting
- [ ] Create polls with multiple options
- [ ] Real-time voting results
- [ ] Poll expiration and scheduling
- [ ] Voting analytics

### Phase 4: Enhanced Features
- [ ] File/image attachments
- [ ] Complaint tracking and status updates
- [ ] Admin dashboard
- [ ] Resident directory
- [ ] Maintenance requests
- [ ] Event management

### Phase 5: Advanced Features
- [ ] Offline-first architecture
- [ ] Dark mode support
- [ ] Multiple language support
- [ ] Advanced analytics
- [ ] Integration with payment systems

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Flutter Team** for the amazing framework
- **Supabase** for the backend-as-a-service platform
- **Material Design** for the design system
- **Community** for inspiration and feedback

---

**Built with ❤️ using Flutter + Supabase**
