🌾 AgriAssist - Smart Agricultural Management Platform
Flutter Firebase Dart Cloudinary Google AI

AgriAssist is a comprehensive Flutter-based mobile application designed to bridge the gap between farmers and agricultural vendors. The platform enables seamless communication, crop management, business networking, and provides AI-powered agricultural assistance with real-time market data integration.

🚀 Key Features
👥 Dual User System
Farmers: Manage crops, connect with vendors, track farming activities, access market prices
Vendors: Browse all farmers' crops, showcase products/services, connect with farmers
Cross-Role Interaction: Farmers can view vendor profiles, vendors can view farmer profiles
Role-Based Navigation: Customized interfaces and features for each user type
🔐 Authentication & Security
Role-Based Login: Separate login screens for farmers and vendors
Firebase Authentication: Secure email/password authentication
User Type Validation: Prevents cross-role login attempts
Profile Verification: User verification system with status indicators
🌱 Advanced Crop Management
Real-Time Crop Updates: Vendors see new crops instantly when farmers add them
Multiple Image Support: Up to 5 images per crop with Cloudinary integration
Growth Stage Tracking: Complete lifecycle monitoring (Seeding → Harvesting)
Advanced Search & Filtering: Filter by category, growth stage, farmer, location
Organic/Conventional Classification: Farming type categorization
Yield Estimation: Track expected and actual yields
🤖 AI-Powered AgriBot
Google Gemini Integration: AI chatbot with agricultural expertise
Role-Based Assistance: Specialized advice for farmers vs vendors
Farmer Support: Crop management, pest control, soil health, weather advice
Vendor Support: Market trends, customer management, supply chain optimization
Real-Time Chat: Instant responses with conversation memory
💰 Live Mandi Prices (Farmers Only)
Government Data Integration: Real-time prices from data.gov.in API
Advanced Filtering: Filter by state, commodity, market location
Price Trend Analysis: Visual indicators for Low/Average/High prices
Smart Caching: 1-hour cache validity for optimal performance
Market Intelligence: Compare prices across different mandis
📸 Professional Image Management
Cloudinary Integration: 25GB free storage with global CDN
Multiple Upload Options: Camera, gallery, or multiple selection
Automatic Optimization: Thumbnail, medium, and large sizes
Real-Time Upload: Images appear instantly with progress indicators
Error Handling: Graceful fallbacks and validation
👤 Real-Time Profile System
Live Profile Updates: Profile data updates instantly using Firebase streams
Native Contact Integration: Call and SMS buttons open device apps
Cross-Role Viewing: Detailed profile screens for farmers and vendors
Location Display: Real-time location updates with visual indicators
Business/Farm Details: Comprehensive information display
💬 Professional Communication
Real-Time Chat: Instant messaging between farmers and vendors
Contact Options: Call, Email, SMS, and in-app chat
User Identification: Clear role indicators and status
Message History: Persistent chat conversations
🗺️ Location & Discovery
Real-Time Location: Automatic location sync across profiles
Nearby Users: Location-based user discovery
Address Validation: Formatted address display
Visual Indicators: Location status with live updates
📱 Screenshots
Coming soon - Screenshots will be added here

🏗️ Project Structure
lib/
├── constants/
│   └── colors.dart              # App color palette and themes
├── models/
│   ├── user.dart               # Base user model
│   ├── farmer.dart             # Farmer-specific model
│   ├── vendor.dart             # Vendor-specific model
│   ├── crop.dart               # Crop data model
│   └── auth_result.dart        # Authentication result model
├── services/
│   ├── auth_service.dart       # Authentication service facade
│   ├── firebase_auth_service.dart     # Firebase authentication
│   ├── firebase_realtime_service.dart # Firebase Realtime Database
│   ├── firebase_init_service.dart     # Firebase initialization
│   ├── crop_service.dart       # Crop management service
│   └── firebase_service.dart   # General Firebase utilities
├── screens/
│   ├── auth/                   # Authentication screens
│   │   ├── user_type_selection_screen.dart
│   │   ├── farmer_login_screen.dart
│   │   ├── vendor_login_screen.dart
│   │   ├── farmer_register_screen.dart
│   │   └── vendor_register_screen.dart
│   ├── home/
│   │   └── home_screen.dart    # Main dashboard
│   ├── crops/
│   │   ├── crops_screen.dart   # Crop listing
│   │   ├── add_crop_screen.dart # Add new crop with image upload
│   │   └── crop_detail_screen.dart
│   ├── profiles/
│   │   ├── farmer_profile_detail_screen.dart
│   │   ├── vendor_profile_detail_screen.dart
│   │   ├── farmers_list_screen.dart
│   │   └── vendors_list_screen.dart
│   ├── chat/
│   │   └── chat_screen.dart    # Real-time messaging
│   ├── profile/
│   │   ├── profile_screen.dart
│   │   └── edit_profile_screen.dart
│   ├── vendors/
│   │   └── vendors_screen.dart # Vendor/Farmer discovery
│   ├── nearby/
│   │   └── nearby_screen.dart  # Location-based discovery
│   ├── farmer_dashboard.dart   # Farmer-specific dashboard
│   └── main_navigation.dart    # Bottom navigation
├── widgets/
│   └── custom_widgets.dart     # Reusable UI components
├── firebase_options.dart       # Firebase configuration
└── main.dart                   # App entry point
🔥 Firebase Integration
Database Structure
Firebase Realtime Database:
├── farmers/
│   └── {uid}/
│       ├── email: string
│       ├── name: string
│       ├── phone: string
│       ├── location: string (real-time)
│       ├── farmingType: string
│       ├── farmAddress: string
│       ├── farmSize: number
│       └── profileImage: string
└── vendors/
    └── {uid}/
        ├── email: string
        ├── name: string
        ├── phone: string
        ├── businessName: string
        ├── businessType: string
        ├── businessAddress: string (real-time)
        └── profileImage: string
Authentication
Firebase Auth for secure user management
Role-based access control
Email/password authentication
User session management
🛠️ Installation & Setup
Prerequisites
Flutter SDK (3.8.1 or higher)
Dart SDK
Android Studio / VS Code
Firebase account
Cloudinary account (free tier)
Git
Installation Steps
Clone the repository

git clone https://github.com/yourusername/agriassist.git
cd agriassist
Install dependencies

flutter pub get
Firebase Setup

Create a new Firebase project at Firebase Console
Enable Authentication (Email/Password)
Enable Realtime Database
Download google-services.json (Android) and GoogleService-Info.plist (iOS)
Place configuration files in respective platform directories
Cloudinary Setup

Create account at cloudinary.com
Create upload preset named agriassist_crops (unsigned mode)
Update lib/config/cloudinary_config.dart with your cloud name:
class CloudinaryConfig {
  static const String cloudName = 'your-cloud-name';
  static const String uploadPreset = 'agriassist_crops';
}
API Configuration

Mandi Prices: Uses Government of India data.gov.in API (included)
AgriBot: Google Gemini API key is configured (demo purposes)
For production: Store API keys securely
Run the application

flutter run
Quick Start Demo
Farmer Login: Use demo credentials or register new account
Vendor Login: Use demo credentials or register new account
Test Features: Add crops, chat with AgriBot, view mandi prices
Real-Time Updates: Open both farmer and vendor apps to see live updates
📦 Dependencies
Core Dependencies
dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.8
  
  # Firebase Backend
  firebase_core: ^3.6.0
  firebase_database: ^11.1.4
  firebase_auth: ^5.3.1
  cloud_firestore: ^5.4.3
  
  # AI & API Integration
  google_generative_ai: ^0.4.3  # Gemini AI Chatbot
  http: ^1.1.0                  # HTTP requests
  
  # Image Management
  cloudinary_public: ^0.21.0    # Cloudinary integration
  image_picker: ^1.0.4          # Camera/Gallery access
  path: ^1.8.3                  # File path utilities
  
  # Native Integration
  url_launcher: ^6.2.2          # Call/SMS functionality

dev_dependencies:
  flutter_test:
    sdk: flutter
  flutter_lints: ^5.0.0
  icons_launcher: ^3.0.2
  flutter_launcher_icons: ^0.14.4
  google_maps_flutter: ^2.13.1
🎯 Advanced Feature Implementation
🤖 AgriBot - AI Assistant
API: Google Gemini 1.5-flash model
Features: Role-based responses, conversation memory, real-time chat
Access: Floating action button + Home screen quick action
Farmer Assistance: Crop management, pest control, soil health, weather advice
Vendor Assistance: Market trends, customer management, supply chain optimization
💰 Live Mandi Prices
Data Source: Government of India data.gov.in API
Features: Real-time prices, advanced filtering, price trend analysis
Caching: 1-hour smart caching for optimal performance
Coverage: Pan-India agricultural commodity prices
Exclusive: Available only to farmers
📸 Cloudinary Image Management
Storage: 25GB free tier with global CDN
Features: Multiple image upload, automatic optimization, real-time preview
Formats: Automatic WebP/JPG selection for optimal loading
Organization: Structured folder system by farmer and crop
Performance: Thumbnail, medium, and large size variants
🔄 Real-Time Updates
Technology: Firebase Realtime Database streams
Features: Instant crop updates, live profile changes, real-time notifications
Performance: Efficient stream-based architecture with minimal rebuilds
User Experience: Live indicators, automatic filtering, smooth transitions
📱 Native Integration
Contact: Call and SMS buttons open device native apps
Camera: Direct camera access for crop photography
Gallery: Multiple image selection from device gallery
Notifications: Real-time snackbar notifications for updates
🔍 Advanced Search & Filtering
Crop Search: Filter by category, growth stage, farmer, location
Mandi Search: Filter by state, commodity, market location
Profile Search: Search across names, locations, business types
Real-Time: Instant search results with debouncing
🚀 Deployment
Android
flutter build apk --release
iOS
flutter build ios --release
Web
flutter build web --release
🧪 Testing
Run Tests
flutter test
Feature Testing
Real-Time Updates: Use test utilities in lib/test_realtime_crops.dart
AgriBot: Test AI responses with different user roles
Mandi Prices: Verify API integration and caching
Image Upload: Test Cloudinary integration with camera/gallery
Authentication: Test role-based login validation
Manual Testing Checklist
 Farmer registration and login
 Vendor registration and login
 Cross-role profile viewing
 Crop addition with multiple images
 Real-time crop updates on vendor screen
 AgriBot conversations (farmer and vendor contexts)
 Mandi price filtering and search
 Call/SMS button functionality
 Real-time profile updates
🔧 Troubleshooting
Common Issues
Authentication Issues
Problem: Login fails or role mismatch
Solution: Ensure Firebase configuration is correct, check user role in database
Image Upload Issues
Problem: Images not uploading to Cloudinary
Solution: Verify Cloudinary cloud name and upload preset configuration
AgriBot Not Responding
Problem: AI chatbot shows errors
Solution: Check internet connection, verify Gemini API key
Mandi Prices Not Loading
Problem: Price data not showing
Solution: Check internet connection, API may have rate limits
Real-Time Updates Not Working
Problem: Crops not appearing instantly
Solution: Ensure Firebase Realtime Database rules allow read/write access
Debug Tips
// Enable debug logging
print('Firebase user: ${FirebaseAuth.instance.currentUser?.uid}');
print('Cloudinary config: ${CloudinaryConfig.cloudName}');
print('Crops stream data: ${crops.length} crops received');
🤝 Contributing
Fork the repository
Create your feature branch (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add some AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a Pull Request
🌐 API Integration Details
Google Gemini AI
Model: gemini-1.5-flash
Temperature: 0.7 (balanced creativity and accuracy)
Max Tokens: 1024
Features: Role-based system prompts, conversation memory
Government Data API
Source: data.gov.in (Government of India)
Dataset: Current Daily Price of Various Commodities from Various Markets
Update Frequency: Daily
Coverage: Pan-India mandi data
Caching: 1-hour validity for optimal performance
Cloudinary CDN
Storage: 25GB free tier
Bandwidth: 25GB/month
Features: Automatic optimization, multiple formats, global CDN
Transformations: Thumbnail (150x150), Medium (400x300), Large (800x600)
🎯 Production Deployment
Environment Configuration
// For production deployment
class ProductionConfig {
  static const String environment = 'production';
  static const bool enableLogging = false;
  static const bool useFirebaseAuth = true;
  
  // Store API keys securely
  static String get geminiApiKey => 
    const String.fromEnvironment('GEMINI_API_KEY');
  static String get cloudinaryCloudName => 
    const String.fromEnvironment('CLOUDINARY_CLOUD_NAME');
}
Security Checklist
 API keys stored in environment variables
 Firebase security rules configured
 Cloudinary upload presets secured
 User input validation implemented
 Error handling for all API calls
🚀 Smart India Hackathon 2024
AgriAssist was developed as a prototype for Smart India Hackathon 2024, addressing the challenge of connecting India's 600+ million farmers with agricultural vendors through digital transformation.

Impact & Vision
Digital Agriculture: Modernizing traditional farming practices
Eliminate Middlemen: Direct farmer-vendor connections
AI-Powered Guidance: Accessible agricultural expertise
Government Integration: Leveraging official data sources
Real-Time Market Access: Instant price and crop information
Demonstration Flow
Dual Authentication: Role-based login system
Crop Management: Real-time crop addition with image upload
AI Assistant: Agricultural guidance via AgriBot
Market Intelligence: Live mandi price analysis
Vendor Marketplace: Browse and discover crops
Communication: Cross-role messaging and contact
Live Updates: Real-time synchronization across users
📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

👨‍💻 Development Team
AgriAssist Development Team

Platform: Flutter 3.8.1+ for cross-platform development
Backend: Firebase (Auth, Realtime Database)
AI Integration: Google Gemini API
Image Management: Cloudinary CDN
Government APIs: data.gov.in integration
🙏 Acknowledgments
Flutter Team: Amazing cross-platform framework
Firebase: Reliable backend services
Google AI: Gemini API for agricultural intelligence
Cloudinary: Professional image management
Government of India: Open data initiative (data.gov.in)
Agricultural Community: Inspiration and feedback
Smart India Hackathon: Platform for innovation
📞 Support & Contact
Technical Support
Issues: Create an issue in this repository
Documentation: Refer to inline code comments
API Issues: Check respective service status pages
Feature Requests
Enhancements: Submit feature requests via GitHub issues
Contributions: Follow the contributing guidelines
Feedback: Agricultural community feedback welcome
Production Support
Deployment: Comprehensive deployment guides included
Monitoring: Built-in error handling and logging
Scaling: Firebase and Cloudinary handle automatic scaling
🌾 Made with ❤️ for India's Agricultural Revolution
Connecting 600+ Million Farmers • Eliminating Middlemen • Empowering Digital Agriculture

AgriAssist - Smart India Hackathon 2024 Prototype
