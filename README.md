# 🎨 COLLABORATIVE WHITEBOARD - HACKATHON PROJECT

## 📁 Project Structure
```
C:\Users\acer\Documents\Default Project\whiteboard\
│
├── server.py    ← Flask + Socket.IO backend
└── static/
    └── index.html ← Beautiful drawing frontend
```

## ▶️ HOW TO RUN THE SOFTWARE

### Step 1: Open Command Prompt
Press `Win + R`, type `cmd`, press Enter

### Step 2: Navigate to the project folder
```
cd "C:\Users\acer\Documents\Default Project\whiteboard"
```

### Step 3: Start the server
```
python server.py
```

### Step 4: Open the app
Open your web browser and go to:
```
http://localhost:5000
```

### Step 5: Share with your team
Give everyone the SAME URL with a room name:
```
http://localhost:5000?room=my-hackathon-room&name=YourName
```

**Example URLs:**
- `http://localhost:5000?room=team-alpha&name=Alex`
- `http://localhost:5000?room=team-alpha&name=Sarah`
- `http://localhost:5000?room=team-alpha&name=Mike`

All users with the same `room` name will draw together in real-time!

## 🎯 HOW TO USE THE APP

### Drawing Controls:
- **Left-drag** on the canvas to draw with your pen color
- **Right-click** or press `E` key to erase (white brush)
- **Esc** key to clear entire canvas (host only)

### Top Right Panel:
- **User list** - See who else is connected
- **Color palette** - Click any color to switch
- **Export button** - Download your drawing as PNG

### Bottom Instructions:
- `Drag` = draw
- `Right-click` or `E` = erase
- `Esc` = clear canvas
- Invite friends using the same room name

## 🏆 HACKATHON DEMO TIPS

### For Judges:
1. **Open 3+ browser windows** with the same room name
2. **Different names** in the URL query params
3. **Draw together** in real-time - see lines appear instantly on all screens!
4. **Test the export** - download the collaborative artwork

### Impress Judges With:
- ✅ Real-time synchronization (technical difficulty)
- ✅ Beautiful UI design (aesthetics)
- ✅ Multiple color choices (personalization)
- ✅ User avatars (identity)
- ✅ Export feature (polished product)

### Talking Points for Judges:
> "This collaborative whiteboard uses Flask-Socket.IO for real-time web communication. When one user draws, the lines are instantly transmitted to all other connected clients via WebSockets. Each user gets a unique color automatically, and we've designed a dark, immersive UI with smooth animations. The app works on mobile too - just open the same URL on your phone!"

## 🔧 TECHNICAL FEATURES

### Backend (server.py):
- Flask web framework
- Socket.IO for real-time WebSocket communication
- Automatic user color assignment (MD5 hash of session ID)
- Drawing history for new users joining late
- User join/leave notifications

### Frontend (index.html):
- Responsive canvas that fits any screen
- Touch support (mobile phones/tablets)
- Color palette with 8 default colors + custom selection
- Eraser mode
- User avatars with colored dots
- Export to PNG
- Keyboard accessibility (Esc to clear)
- Animated background with CSS gradients
- Reduced motion support

### Real-time Mechanics:
1. User draws on canvas → `mousemove` event
2. Data emitted to server via `socket.emit('draw', {...})`
3. Server broadcasts to ALL other clients via `socket.emit('draw', data)`
4. Other clients' `socket.on('draw', ...)` receives data
5. Each client draws on their own canvas

## 🚀 EXTENSION IDEAS (Add More Features)

If you have time before the hackathon, add these:

1. **Shapes**: Detect rectangles, circles when user holds Shift
2. **Undo/Redo**: Stack-based history
3. **Multiple rooms**: Different URL room names
4. **Chat messages**: Text chat alongside drawing
5. **Image import**: Load background images
6. **User counts**: Real-time participant count
7. **Password-protected rooms**: `?room=secret&password=123`
8. **Save to file**: Export drawing data as JSON

## 📊 PROJECT DIFFICULTY
- **Complexity**: Medium (real-time WebSockets + Canvas drawing)
- **Time to build**: ~2 hours
- **Hackathon potential**: High (impressive demo, technical depth)
- **Unique value**: Most simple whiteboards don't have the beautiful design + real-time sync + easy sharing

## ❓ TROUBLESHOOTING

**Server won't start?**
- Make sure Python 3 is installed: `python --version`
- Install dependencies: `pip install flask flask-socketio`
- Check if port 5000 is already in use

**Can't connect?**
- Ensure ALL users use the SAME room name
- Ensure ALL users open the URL from the same network (or use ngrok for external access)
- Check browser console for Socket.IO connection errors

**Canvas not drawing?**
- Make sure you've clicked on the canvas first
- Touch devices: tap once to focus, then draw

---

## 🎉 READY FOR THE HACKATHON!

Your collaborative whiteboard is unique because it combines:
1. ✅ **Beautiful, unique design** (not another boring white)
2. ✅ **Real-time technology** (impressive technical feat)
3. ✅ **Easy sharing** (just send the URL)
4. ✅ **Mobile-responsive** (works on phones too)
5. ✅ **Polished UI/UX** (judges love aesthetics)

**Good luck at your hackathon! 🏆**

---
*Built with Flask, Socket.IO, and a lot of CSS love.*