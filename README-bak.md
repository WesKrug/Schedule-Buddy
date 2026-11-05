## Shuddy - Scheduling Buddy App

### Introduction
Shuddy is a scheduling application that allows multiple users to combine their schedules to easily find times when all parties are free. The app provides a simple UI with color-coded and textured blocks to visualize schedules and time blocks.

### Key Features
- **Group Collaboration**: Create groups and generate unique group links for collaboration.
- **Anonymous Profiles**: Users can join groups anonymously by providing their name and selecting a color.
- **Visual Schedule Comparison**: View calendars with color-coded blocks representing each user's blocked time slots.
- **Google Calendar Integration**: Seamlessly pull in authenticated Google Calendar data for schedule management.
- **No Login Required**: Start using Shuddy immediately without needing to create an account.

### Technical Architecture
- **Database**: PostgreSQL for relational data storage.
- **ORM**: Rails' Active Record for database interactions.
- **Authentication**: Devise gem for user authentication (optional for anonymous profiles).
- **Authorization**: Pundit gem for role-based access control.
- **Calendar Integration**: Google Calendar API for external calendar synchronization.

### Database Schema Overview
Shuddy's database includes the following core entities:
- **Users**: Store user information (name, color, timestamps).
- **Groups**: Manage shared schedules with creator information and descriptions.
- **User-Group Relationships**: Many-to-many associations between users and groups.
- **Blocked Times**: Track time blocks for individual users within groups.

### Getting Started
1. Clone the repository
2. Set up your PostgreSQL database
3. Configure Google Calendar API credentials
4. Run `bundle install` to install dependencies
5. Start the Rails server with `rails server`

### Contributing
Shuddy is open to contributions! Please refer to the [CONTRIBUTING.md](CONTRIBUTING.md) file for guidelines on how to contribute to the project.

### Backend Startup
Run the following command to start Ubuntu `wsl.exe -d Ubuntu`