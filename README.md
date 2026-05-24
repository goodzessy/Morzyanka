# VibMess - Modern Group Messenger & Calls

**VibMess** is a real-time messaging and group calling application built with React, Firebase Realtime Database, and Tailwind CSS.

## Features

✨ **Core Messaging**
- Real-time text messaging in private & group chats
- User authentication with SHA-256 password hashing
- Message timestamps and delivery status
- Bilingual support (English & Russian)
- Dark/Light theme toggle

📞 **Group Calls**
- Audio group calling support
- Real-time participant tracking
- WebRTC-ready architecture
- Call state management (idle, calling, connected)
- Visual call UI with participant avatars

👥 **User Management**
- User registration and login
- User profiles with status tracking
- Online/offline presence detection
- Group chat creation
- Member management in groups

🎨 **UI/UX**
- Clean, modern interface with Tailwind CSS
- Smooth animations with Framer Motion
- Lucide icons throughout
- Responsive design (desktop-first)
- Custom scrollbars

🌍 **Multilingual**
- Full English support
- Full Russian (Русский) support
- Easy language switching in settings

## Tech Stack

- **Frontend**: React 18
- **Styling**: Tailwind CSS
- **Animations**: Framer Motion
- **Icons**: Lucide React
- **Backend**: Firebase Realtime Database
- **Authentication**: SHA-256 hashing (client-side)

## Installation

### Prerequisites
- Node.js 14+ (optional, for local development)
- Firebase project (for real-time database)
- Modern web browser

### Quick Start (No Installation Needed)

Open `index.html` directly in your browser. The app works completely client-side with Firebase as backend.

**For development with a local server:**

```bash
npm install -D http-server
npx http-server
```

Then navigate to `http://localhost:8080` in your browser.

## Firebase Configuration

Update the Firebase config in `index.html` (line ~215):

```javascript
const firebaseConfig = {
    databaseURL: "https://your-project-rtdb.firebaseio.com/"
};
```

Get your database URL from Firebase Console:
1. Go to [Firebase Console](https://console.firebase.google.com)
2. Create a new project or select existing
3. Create Realtime Database
4. Copy your database URL
5. Replace in `index.html`

## Usage

### Registration
1. Click "Don't have an account?"
2. Enter username and password
3. Click "Register"

### Login
1. Enter username and password
2. Click "Log In"

### Creating Chats
- **Groups**: Click "New Group" button
- **Private**: Search for user in search bar

### Sending Messages
1. Select a chat
2. Type in message input
3. Press Send or Enter

### Group Calls
1. Open a group chat
2. Click "Group Call" icon (👥)
3. Participants will see incoming call notification
4. Click to join or decline

### Settings
- Click ⚙️ icon
- Toggle theme (Dark/Light)
- Change language (EN/RU)
- Log out

## Database Structure

```
users/
  {userId}/
    id: string
    username: string
    password: string (hashed)
    language: string
    theme: string
    status: string (online/offline)

chats/
  {chatId}/
    id: string
    name: string
    type: string (private/group)
    members: { userId: true }
    lastMessage: string
    lastTimestamp: number
    creatorId: string

messages/
  {chatId}/
    {messageId}/
      senderId: string
      senderName: string
      text: string
      type: string (text)
      timestamp: number
```

## Roadmap

- [ ] Voice/Video messaging
- [ ] File sharing
- [ ] Message reactions & emojis
- [ ] Message edit/delete
- [ ] User presence indicators
- [ ] Read receipts
- [ ] Message search
- [ ] Sticker packs
- [ ] Bot integration
- [ ] Channel support

## Browser Support

- Chrome/Edge: ✅ Full support
- Firefox: ✅ Full support
- Safari: ✅ Full support
- Mobile browsers: ✅ Responsive

## Performance

- Lightweight (~35KB single file)
- Real-time updates with Firebase listeners
- Optimized React rendering
- Minimal bundle size (CDN-based)

## Security Notes

⚠️ **Development Version**
- Passwords hashed with SHA-256 on client
- For production, implement server-side validation
- Use Firebase security rules to restrict database access
- Never expose Firebase config in production

## Contributing

Feel free to fork and submit pull requests with improvements!

## License

MIT License - feel free to use and modify for your projects.

## Support

For issues or questions:
1. Check existing issues on GitHub
2. Create new issue with detailed description
3. Include browser/OS information

## Credits

Built with ❤️ by VibMess Team

---

**Last Updated**: May 2026