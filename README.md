
readme_content = """# WeChat Simulator

A modern, interactive HTML-based WeChat chat interface simulator with AI auto-reply functionality.

## Features

### User Interface
- **Modern Design**: Clean, minimalist interface inspired by WeChat's desktop application
- **Responsive Layout**: Fixed 900x600px container with flexible internal components
- **Dark Sidebar**: Left panel with dark grey (#2e2e2e) background for user info and contacts
- **White Chat Area**: Right panel with light background for message display

### User Information Bar
- **Circular Avatar**: Emoji-based avatar with hover animation (scales on hover)
- **User Details**: Displays "My WeChat" name and WeChat ID "me123"
- **Click to Change**: Click the avatar to randomly cycle through 100+ emojis

### Search Functionality
- **Real-time Filtering**: Search contacts as you type
- **Instant Results**: Contacts hide/show dynamically based on search input
- **Case-insensitive**: Works with any capitalization

### Contact List
- **Two Default Contacts**: Xiaoming and Xiaohong
- **Active State Highlighting**: Selected contact gets darker background
- **Message Previews**: Shows the last message sent/received in each chat
- **Click to Open**: Opens the corresponding chat window on the right

### Chat Window
- **Welcome Message**: Displays a personalized welcome for each contact
- **Message History**: Messages persist during the session per contact
- **Auto-scroll**: Automatically scrolls to the latest message

### Messaging System
- **Send Messages**: Type in the input box and press Enter or click Send
- **Message Bubbles**: Green for sent messages, white for received messages
- **Timestamps**: Each message shows the time it was sent
- **Typing Indicator**: Animated dots appear while AI is "typing"

### AI Auto-Reply
The AI responds based on keywords detected in user messages:

| Keyword | Response |
|---------|----------|
| hello, hi | Friendly greeting |
| how are you | Status inquiry response |
| what is your name, name | Self-introduction |
| weather | Weather comment |
| time | Current time |
| help | Usage guidance |
| bye, goodbye | Farewell message |
| thank, thanks | Gratitude response |
| love | Affectionate response |
| sad | Comforting message |
| happy | Celebration response |
| joke | Random joke |
| food, music, movie, book, game | Topic-specific engagement |
| work, study | Encouragement |
| sleep, dream | Rest-related comment |
| *(default)* | Generic interest response |

### Avatar Customization
- **User Avatar**: Click to change your own emoji
- **Contact Avatars**: Click any contact's avatar to change their emoji
- **100+ Emojis**: Includes faces, people, animals, and more
- **Persistent Updates**: Changes reflect immediately in all messages

## File Structure

```
wechat_simulator.html
├── CSS Styles (embedded)
│   ├── Layout & Container
│   ├── Sidebar Components
│   ├── Chat Area Components
│   ├── Message Bubbles
│   └── Animations
├── JavaScript (embedded)
│   ├── State Management
│   ├── Chat Logic
│   ├── AI Response Engine
│   ├── Search Functionality
│   └── Emoji Randomizer
└── HTML Structure
    ├── Sidebar (User Info + Search + Contacts)
    └── Chat Area (Header + Messages + Input)
```

## Technical Details

### Technologies Used
- **HTML5**: Semantic structure
- **CSS3**: Flexbox layout, transitions, animations, shadows
- **Vanilla JavaScript**: No external dependencies

### Browser Compatibility
- Chrome, Firefox, Safari, Edge (latest versions)
- IE11+ (with limited animation support)

### Key Implementation Details
- **Pure Client-side**: All logic runs in the browser, no server required
- **Session Storage**: Chat history persists during the browser session
- **Event Delegation**: Efficient click handling for dynamic elements
- **CSS Animations**: Smooth transitions and typing indicator animation

## How to Use

1. **Open the HTML file** in any modern web browser
2. **Select a contact** from the left sidebar (Xiaoming or Xiaohong)
3. **Type a message** in the input box at the bottom
4. **Press Enter** or click the **Send** button
5. **Wait for AI reply** (1.5-2.5 seconds with typing animation)
6. **Click any avatar** to randomly change its emoji
7. **Use the search box** to filter contacts by name

## Customization

### Adding New Contacts
Add a new `.chat-item` div in the sidebar:

```html
<div class="chat-item" data-contact="NewName" onclick="openChat('NewName')">
    <div class="chat-avatar" id="avatar-NewName" onclick="event.stopPropagation(); changeEmoji('NewName')">🆕</div>
    <div class="chat-info">
        <div class="chat-name">NewName</div>
        <div class="chat-preview" id="preview-NewName">Welcome to chat!</div>
    </div>
</div>
```

Then add to the JavaScript:
```javascript
contactEmojis['NewName'] = '🆕';
chatHistory['NewName'] = [];
```

### Adding AI Responses
Add new keyword-response pairs to the `aiResponses` object:

```javascript
const aiResponses = {
    'newkeyword': 'Your custom response here!',
    // ... existing responses
};
```

### Changing Default Emojis
Modify the `emojis` array to include your preferred emoji set.

### Styling Changes
All styles are embedded in the `<style>` tag. Key color variables:
- Primary green: `#07c160`
- Sidebar background: `#2e2e2e`
- Sent message bubble: `#95ec69`
- Received message bubble: `#fff`

## Demo Keywords to Try
- "Hello" - Greeting
- "What is your name" - Introduction
- "Tell me a joke" - Entertainment
- "How is the weather" - Small talk
- "I feel sad" - Emotional support
- "Thank you" - Politeness test
- "Goodbye" - End conversation

## License
Open source - feel free to modify and distribute.

## Author
Created as a demonstration of HTML/CSS/JavaScript capabilities.
"""

with open('/mnt/agents/output/readme.md', 'w', encoding='utf-8') as f:
    f.write(readme_content)

print("README.md created successfully!")
print(f"File size: {len(readme_content)} characters")
