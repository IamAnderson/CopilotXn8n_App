# Calendar Assistant Chat Application

A modern, professional React chat application designed for enterprise use. Features a WhatsApp-like interface optimized for narrow sidebars (300-400px width) with seamless integration to n8n webhook endpoints.

## Features

### 🎨 **Modern UI/UX**
- Clean, professional chat interface similar to WhatsApp Web
- User messages aligned right (blue background)
- Bot messages aligned left (gray background with border)
- Responsive design optimized for narrow sidebars
- Smooth animations and typing indicators
- Custom scrollbar styling

### 💬 **Chat Functionality**
- Real-time message display with timestamps
- Auto-scroll to newest messages
- Enter key support for sending messages
- Input field disabled during API calls
- Typing indicator with animated dots
- Error handling with user-friendly messages

### 🔗 **API Integration**
- POST requests to configurable webhook URL
- JSON payload: `{ "message": "user message text" }`
- Expects JSON response: `{ "output": "bot response text" }`
- Graceful error handling for network issues
- CORS-ready implementation

### 📱 **Responsive Design**
- Optimized for 300-400px width sidebars
- Mobile-friendly responsive breakpoints
- Professional enterprise-ready styling
- Accessibility-focused design

## Quick Start

### Prerequisites
- Node.js 18+ 
- npm or yarn

### Installation

1. **Clone and install dependencies:**
```bash
git clone <repository-url>
cd copilotxn8n_app
npm install
```

2. **Configure your webhook URL:**
   
   Edit `src/App.tsx` and update the webhook URL:
   ```typescript
   const WEBHOOK_URL = "https://YOUR_N8N_URL/webhook/calendar-bot"
   ```

3. **Start development server:**
```bash
npm run dev
```

4. **Open your browser:**
   Navigate to `http://localhost:5174` (or the port shown in terminal)

### Production Build

```bash
npm run build
npm run preview
```

## Configuration

### Webhook Integration

The application sends POST requests to your n8n webhook with this format:

**Request:**
```json
{
  "message": "user message text"
}
```

**Expected Response:**
```json
{
  "output": "bot response text"
}
```

### Customization

#### Styling
- **Colors:** Modify Tailwind classes in `src/App.tsx`
- **Layout:** Adjust responsive breakpoints in `src/App.css`
- **Animations:** Customize timing in CSS animations

#### Behavior
- **Welcome Message:** Edit the initial message in `App.tsx` line 39
- **Error Messages:** Customize error text in the `sendMessage` function
- **Typing Delay:** Adjust animation delays in the typing indicator

## Technical Stack

- **React 19** with TypeScript
- **Vite** for fast development and building
- **Tailwind CSS** for styling
- **Fetch API** for HTTP requests
- **React Hooks** for state management

## File Structure

```
src/
├── App.tsx          # Main chat component
├── App.css          # Custom styles and responsive design
├── index.css        # Tailwind directives
├── main.tsx         # React app entry point
└── assets/          # Static assets
```

## Browser Support

- Chrome/Edge 88+
- Firefox 78+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Development

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint

### Key Components

1. **Message Interface:** TypeScript interface for type safety
2. **State Management:** React hooks for messages, loading, and errors
3. **API Integration:** Fetch-based webhook communication
4. **Auto-scroll:** Automatic scrolling to newest messages
5. **Error Handling:** Comprehensive error states and user feedback

## Troubleshooting

### Common Issues

**CORS Errors:**
- Ensure your n8n webhook allows cross-origin requests
- Check browser console for specific CORS error details

**Styling Issues:**
- Verify Tailwind CSS is properly configured
- Check that PostCSS is processing the CSS files

**API Connection:**
- Verify webhook URL is correct and accessible
- Test webhook endpoint independently with tools like Postman

### Performance

The application is optimized for:
- Fast initial load times
- Smooth scrolling with large message histories
- Efficient re-renders using React best practices
- Minimal bundle size with tree-shaking

## License

This project is licensed under the MIT License.
