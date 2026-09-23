# OtChaim

OtChaim is a modern emergency event management system designed to facilitate rapid response, user subscription management, and real-time notifications. Built with .NET and MAUI for cross-platform support, it leverages a clean architecture for maintainability and scalability.

## 🚀 Features
- Emergency event creation, tracking, and resolution
- User subscription and approval workflow
- Real-time notifications and status updates
- Modular architecture with clear separation of concerns
- Cross-platform UI with MAUI
- **Tabbed Navigation**: Tool and Settings tabs with swipe navigation
- **Elderly-Accessible Design**: Large fonts, buttons, and high contrast
- **Emergency Management**: Type selection, contact management, and status tracking
- **User Information Management**: Personal, medical, and emergency contact data

## 🏗️ Project Structure
- `OtChaim.Domain/` - Core domain models and business logic
- `OtChaim.Application/` - Application layer, CQRS handlers, and commands
- `OtChaim.Persistence/` - Data access and repository implementations
- `OtChaim.Presentation.MAUI/` - Cross-platform UI (MAUI)
- `*.Tests/` - Unit and integration tests for each layer

## 📱 UI/UX Design

### Main Navigation Structure
- **Tool Tab**: Contains Emergency Dashboard, Emergency, and Group Status screens
- **Settings Tab**: Contains User Information, Medical Information, and Emergency Contacts screens
- **Swipe Navigation**: Users can swipe between screens within each tab
- **COM-MIT Branding**: Logo appears in top-left of all screens
- **Mood Indicators**: Smiley face (Tool tab) and sad face (Settings tab) in top-right

### Tool Tab Screens

#### Emergency Dashboard
- Real-time emergency monitoring and management
- Emergency creation with type and severity selection
- User status tracking (Safe/Not Safe)
- Emergency resolution workflow

#### Emergency Screen
- Emergency type selection with left/right navigation arrows
- Contact list display (Group/Single/Email/SMS/Messenger)
- Attachment buttons (Pic, Pers Info, Med Info, GPS, Docu)
- Customizable emergency message with +/- management
- Large red "EMERGENCY!" button

#### Group Status Screen
- Group selection with navigation arrows
- Contact list with profile pictures and status indicators
- Status indicators: green "ok", yellow "?", red "!", red ":D"
- Large yellow "Are you ok?" button
- Contact management (+/- buttons)

### Settings Tab Screens

#### User Information Screen
- Profile picture upload functionality
- Personal information form (First name, Last name, Birthday, Weight, Blood type)
- Contact information display (Address, Current Location, Phone, Email)
- GPS location integration
- Data management (+/- buttons)

#### Medical Information Screen
- Medical condition selection with navigation arrows
- Medical information form (Condition, Medication, Information)
- Large text area for additional medical information
- Medical data management (+/- buttons)

#### Emergency Contacts Screen
- Contact selection with navigation arrows
- Contact information form (First name, Last name, Birthday, Blood type)
- Contact details display (Address, Phone, Email)
- Nickname system for internal contact names
- Contact management (+/- buttons)

### Design Philosophy

#### Elderly Accessibility
- **Large Fonts**: Minimum 18px for body text, 24px+ for headers
- **Large Buttons**: Minimum 60px height for main buttons
- **Rounded Corners**: 16px radius for all UI elements
- **High Contrast**: Clear color scheme with good contrast ratios

#### Low-Stress Visuals
- **Smooth Transitions**: CarouselView for swipe navigation
- **Rounded Elements**: No sharp edges or panic-inducing visuals
- **Consistent Spacing**: 20px padding and spacing throughout
- **Clear Visual Hierarchy**: Proper use of typography and colors

### Color Scheme
- **Primary**: #ee5547 (Red for emergency actions)
- **Secondary**: #ffc44e (Yellow for backgrounds and confirmations)
- **White**: #FFFFFF (For content areas)
- **Gray Scale**: Various shades for text and borders

## 🛠️ Getting Started
### Prerequisites
- [.NET 10+ SDK](https://dotnet.microsoft.com/download)
- (Optional) [MAUI workload](https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation)

### Build & Run
```sh
# Restore dependencies
dotnet restore
# Build all projects
dotnet build
# Run MAUI app (example for Windows)
dotnet run --project OtChaim.Presentation.MAUI
```

### Running Tests
```sh
dotnet test
```

## 📁 Technical Implementation

### MAUI File Structure
```
OtChaim.Presentation.MAUI/
├── Pages/
│   ├── Tool/
│   │   ├── ToolTabPage.xaml/.cs
│   │   ├── ToolTabViewModel.cs
│   │   ├── EmergencyDashboardPage.xaml/.cs
│   │   ├── EmergencyPage.xaml/.cs
│   │   ├── EmergencyViewModel.cs
│   │   ├── GroupStatusPage.xaml/.cs
│   │   └── GroupStatusViewModel.cs
│   └── Settings/
│       ├── SettingsTabPage.xaml/.cs
│       ├── SettingsTabViewModel.cs
│       ├── UserInfoPage.xaml/.cs
│       ├── UserInfoViewModel.cs
│       ├── MedicalInfoPage.xaml/.cs
│       ├── MedicalInfoViewModel.cs
│       ├── EmergencyContactsPage.xaml/.cs
│       └── EmergencyContactsViewModel.cs
├── ViewModels/
│   └── EmergencyDashboardViewModel.cs
├── Services/
│   └── NavigationService.cs
├── Converters/
│   ├── NotNullConverter.cs
│   ├── NullConverter.cs
│   └── InverseBoolConverter.cs
└── Resources/
    └── Images/
        ├── commit_logo.png
        ├── smiley_face.png
        ├── sad_face.png
        ├── profile_picture.png
        ├── emergency_icon.png
        └── settings_icon.png
```

### Key Components

#### Navigation Service
- Handles screen transitions
- Provides navigation between pages
- Error handling for navigation failures

#### Value Converters
- `NotNullConverter`: Shows content when value is not null
- `NullConverter`: Shows content when value is null
- `InverseBoolConverter`: Inverts boolean values

#### Custom Button Styles
- `EmergencyButton`: Large red button for emergency actions
- `AreYouOkButton`: Large yellow button for status checks
- `AttachmentButton`: Small circular buttons for attachments
- `MessageButton`: Small circular buttons for management

## 🎯 Usage

### Navigation
The app automatically starts with the Tool tab selected. Users can:
1. Tap the "Tool" or "Settings" tab to switch between main sections
2. Swipe left/right within each tab to navigate between screens
3. Use the navigation arrows to change sub-sections (emergency types, groups, contacts, etc.)

### Data Entry
- All form fields support large text input for elderly users
- Date pickers and dropdowns are sized appropriately
- GPS location is automatically detected where available

### Emergency Features
- Emergency button triggers confirmation dialog
- "Are you ok?" button shows priority overlay
- Status indicators provide clear visual feedback

## 🔮 Future Enhancements
- Implement actual image upload functionality
- Add GPS location services integration
- Connect to backend services for data persistence
- Add haptic feedback for important actions
- Implement accessibility features (voice-over, screen reader support)

## 🤝 Contributing
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes
4. Open a Pull Request

Please follow the code style and add tests for new features.

## 📄 License
This project is licensed under the GNU GPLv3. See [LICENSE](LICENSE) for details.
