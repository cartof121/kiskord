# Reddit Posts for Kiskord

## r/webdev

**Title:**
I built a P2P voice chat app with Discord-quality audio processing in the browser (WebRTC + RNNoise)

**Post:**
Hey r/webdev! 👋

I just finished building **Kiskord** - a privacy-focused, peer-to-peer voice chat application that runs entirely in your browser. No sign-ups, no servers storing your voice data, just direct P2P connections.

**Live Demo:** https://kiskord.netlify.app/
**GitHub:** https://github.com/Lafun-code/kiskord

### What makes it interesting?

🎵 **Professional Audio Chain**
- RNNoise (AI-powered noise suppression using WASM)
- High-pass filters, noise gates, voice EQ, de-esser, and limiter
- Multiple quality modes (Basic → Ultra/Discord-level)
- Voice Activity Detection

🔒 **Privacy First**
- True P2P using WebRTC - no audio goes through servers
- Anonymous login (just enter a nickname)
- No data storage or recordings

🛠️ **Tech Stack**
- React 18 + TypeScript
- WebRTC for P2P connections
- Firebase (only for signaling/ICE exchange)
- Web Audio API for professional audio processing
- Tailwind CSS for UI

### Technical Highlights

The most challenging part was creating the audio processing pipeline. I implemented a full chain similar to Discord's:

```
Mic → DC Blocker → HPF → Spectral Gate → Noise Gate 
→ RNNoise → EQ → De-Esser → Compressor → Limiter → Output
```

All processing happens in real-time using Web Audio API and AudioWorklets. The RNNoise integration via WASM was particularly fun to implement.

### Try It Out

1. Open https://kiskord.netlify.app/
2. Create a room
3. Share the room ID with a friend
4. Start talking!

Would love to hear your feedback, especially on the audio quality and any bugs you encounter. Open source and MIT licensed, so feel free to check out the code!

What do you think? Any suggestions for improvements?

---

## r/reactjs

**Title:**
Built a real-time P2P voice chat with React + WebRTC + RNNoise (Discord-like audio quality)

**Post:**
Hey React devs! 🚀

Just launched **Kiskord** - a voice chat app built with React that implements professional-grade audio processing in the browser.

**Try it:** https://kiskord.netlify.app/
**Source:** https://github.com/Lafun-code/kiskord

### Tech Stack
- **React 18** with TypeScript
- **WebRTC** for P2P connections
- **Firebase** for signaling/authentication
- **Vite** for blazing fast dev experience
- **Tailwind CSS** for styling
- **RNNoise** (WASM) for AI noise suppression

### Interesting React Patterns Used

**Custom WebRTC Hook**
```typescript
const { participants, isMuted, toggleMute, voiceLevel } = 
  useWebRTC(roomId, user, audioOptions);
```

One hook manages all WebRTC connections, audio processing, and state. Had to carefully manage refs for audio nodes to avoid memory leaks.

**Context for Auth**
Anonymous Firebase auth wrapped in a context provider - keeps things clean.

**Real-time Updates**
Using Firebase Firestore snapshots for participant management and connection signaling.

### Performance Considerations

- Audio processing runs on AudioWorklet (separate thread)
- Cleanup on unmount is crucial - peer connections, audio nodes, etc.
- Used Map/Set for O(1) participant lookups
- Memoized components to avoid unnecessary re-renders

### Features
- 🎙️ Crystal-clear audio with noise suppression
- 👥 Multiple participants per room
- 📊 Real-time speaking indicators
- 🎚️ Self-monitoring (hear yourself)
- 🌙 Dark mode UI

The app is live and fully functional. Would love feedback from the React community!

---

## r/opensource

**Title:**
Kiskord - Open-source P2P voice chat with professional audio processing (Discord alternative)

**Post:**
Hey everyone! 👋

I'm excited to share **Kiskord** - an open-source, privacy-focused voice chat application I built as a Discord alternative for simple voice calls.

**🌐 Live:** https://kiskord.netlify.app/
**📦 GitHub:** https://github.com/Lafun-code/kiskord
**📄 License:** MIT

### Why I Built This

I wanted a simple voice chat solution that:
- Doesn't require account creation
- Keeps conversations private (P2P, no server recording)
- Works in any modern browser
- Offers professional audio quality
- Is completely open source

### Key Features

**Privacy**
- True peer-to-peer connections (WebRTC)
- No voice data stored on servers
- Anonymous usage - just pick a nickname
- Open source - audit the code yourself

**Audio Quality**
- AI-powered noise suppression (RNNoise)
- Professional audio chain: filters, gates, EQ, compression
- Multiple quality modes
- Voice activity detection

**Easy to Use**
- No installation required
- Share a room link, start talking
- Works on desktop and mobile browsers

### Tech Stack (All Open Source)
- React + TypeScript
- WebRTC
- RNNoise (Mozilla/Xiph)
- Firebase (only for signaling)
- Tailwind CSS

### Contributing

The project is MIT licensed and contributions are welcome! Some areas that could use help:

- Mobile browser optimization
- Screen sharing feature
- Better error handling
- More audio processing options
- Internationalization

Check out the GitHub repo if you're interested in contributing or just want to see how it's built.

Would love to hear your thoughts and suggestions! 🎉

---

## r/SideProject

**Title:**
I built a Discord-like voice chat app that works in your browser - no sign-up needed! (P2P + AI noise suppression)

**Post:**
Hey r/SideProject! 

After months of work, I finally launched my side project: **Kiskord** - a voice chat app that focuses on privacy and audio quality.

**🚀 Live Demo:** https://kiskord.netlify.app/
**💻 GitHub:** https://github.com/Lafun-code/kiskord

### The Idea

I was frustrated with needing accounts for everything and wanted a simple "send a link, start talking" solution with good audio quality. Think Discord, but:
- No account needed
- True P2P (privacy-focused)
- Browser-based (no download)
- Open source

### What It Does

1. **Create a room** - Click one button
2. **Share the link** - Send to friends
3. **Start talking** - That's it!

### Technical Stuff (for the nerds 🤓)

- **Frontend:** React + TypeScript + Tailwind CSS
- **P2P:** WebRTC for direct connections
- **Audio:** Web Audio API with RNNoise WASM for noise suppression
- **Backend:** Firebase (just for signaling, not audio data)

The coolest part? I implemented a full professional audio processing chain:
- AI noise suppression
- High-pass filters (removes fan noise)
- Voice EQ
- Dynamic compression
- Peak limiting

All running in your browser in real-time!

### Challenges

- Getting RNNoise WASM to work with AudioWorklets
- Managing audio node lifecycle (memory leaks are real!)
- WebRTC connection state management
- Cross-browser compatibility

### Future Plans

- Screen sharing
- Text chat
- Custom room URLs
- More audio settings

Try it out and let me know what you think! It's completely free and open source (MIT license).

### Screenshots

(You can add screenshots from the app)

Happy to answer any questions about the tech or the project! 🎙️

---

## r/privacy

**Title:**
Privacy-focused voice chat alternative to Discord (P2P, no sign-up, open source)

**Post:**
For those looking for a privacy-respecting voice chat solution, I built **Kiskord**.

**Try it:** https://kiskord.netlify.app/
**Source Code:** https://github.com/Lafun-code/kiskord

### Privacy Features

**No Data Collection**
- No account required - just enter a nickname
- No email, phone number, or personal info
- No analytics or tracking

**True Peer-to-Peer**
- Direct WebRTC connections between users
- Voice data never touches our servers
- End-to-end connection (as private as a phone call)

**Transparent & Auditable**
- Fully open source (MIT license)
- All code is on GitHub
- Self-hostable

**Minimal Server Usage**
- Firebase only used for:
  - Anonymous authentication
  - WebRTC signaling (exchanging connection info)
- No audio/voice data stored
- No conversation logs

### How It Works

WebRTC creates direct peer-to-peer connections. The server is only used to help establish these connections (signaling), similar to how a phone network connects two callers. Once connected, all audio goes directly between users.

### For the Technical Folks

- Uses STUN servers for NAT traversal (Google's public STUN server)
- SDP and ICE candidates exchanged via Firestore
- Audio processing done locally via Web Audio API
- No server-side audio processing or storage

### Comparison

| Feature | Kiskord | Discord | Zoom |
|---------|---------|---------|------|
| Account Required | ❌ | ✅ | ✅ |
| P2P Audio | ✅ | ❌ | ❌ |
| Open Source | ✅ | ❌ | ❌ |
| Self-hostable | ✅ | ❌ | ❌ |
| Audio Recording | ❌ | Optional | Optional |

Not saying Kiskord replaces these services, but if you need a quick, private voice call without accounts or data collection, this might work for you.

Feedback welcome! 🔒

---

## Kullanım Talimatları

1. **Subreddit seçin** ve kurallarını okuyun
2. **Post başlığını ve içeriğini** kopyalayın
3. **Flair ekleyin** (varsa): "Show and Tell", "Project", "Launch" gibi
4. Eğer subreddit izin veriyorsa **screenshot ekleyin**
5. **Yorumlara yanıt verin** - engagement önemli!

### Öneriler:
- Tüm subreddit'lere aynı anda atmayın (spam gibi görünür)
- Her post için farklı günler seçin
- Yorumlara hızlıca yanıt verin
- Eleştirilere açık olun ve teşekkür edin

### Zamanlama:
- **En iyi saatler:** 
  - Hafta içi: 8-10 AM EST veya 1-3 PM EST
  - Hafta sonu: 8-11 AM EST
- Salı-Perşembe genelde en aktif günler

Başarılar! 🚀
