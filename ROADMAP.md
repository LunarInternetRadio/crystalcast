# Icecast Rewrite: Features & Considerations

## 🔑 Core Functionality
- **Protocol Support**
  - HTTP streaming
  - Shoutcast compatibility
  - WebSocket support
  - HTTPS/TLS
  - Adaptive streaming (HLS, DASH)
- **Stream Formats**
  - Ogg (Vorbis, Opus, Theora)
  - MP3
  - AAC / HE-AAC
  - WebM/Opus
  - Future container flexibility
- **Source Connections**
  - Push model (ices2, butt, ezstream style)
  - Pull/relay streams
  - Live encoding passthrough
  - Auto-DJ (file/directory playout)
- **Client Handling**
  - Multiple listeners
  - Connection limits (per mount/server/user)
  - Efficient socket/memory handling
  - Buffering/jitter control

## ⚙️ Server & Architecture
- **Configuration**
  - YAML/JSON/TOML (instead of XML)
  - Hot reload
  - Global vs. per-mount config
- **Mountpoints**
  - Multiple streams per server
  - Per-mount authentication
  - Per-mount transcoding/normalization
- **Performance**
  - Async I/O (epoll/kqueue/libuv)
  - Scalable threading or async event loop
  - Resource monitoring (CPU, RAM, bandwidth)
  - Clustering & horizontal scaling
- **Persistence & State**
  - Graceful restart (retain clients)
  - Stream failover
  - Persistent metadata

## 🔒 Security & Access Control
- **Authentication**
  - Basic auth
  - Token-based (JWT, OAuth2)
  - External hooks (LDAP, API)
- **Authorization**
  - Roles: admin, source, listener
  - Per-mount restrictions
  - Geo/IP filtering
- **Encryption**
  - TLS with Let’s Encrypt integration
  - Secure client ↔ server & source ↔ server

## 📊 Monitoring & Admin
- **Web Interface**
  - Dashboard (listeners, sources, relays)
  - Stream stats (bitrate, codec, uptime, metadata)
  - Mount management (kick, set metadata)
- **APIs**
  - REST/GraphQL
  - Prometheus/metrics endpoint
  - Webhooks for stream events
- **Logging & Analytics**
  - Access logs
  - Error logs
  - Historical stats (peaks, geo, counts)

## 🎵 Metadata Handling
- Dynamic metadata updates (title/artist)
- Inline metadata (ICY protocol)
- External metadata sources (API hooks)
- Shoutcast/ICY compatibility

## 🌐 Advanced Features
- **Load Balancing**
  - Relays between nodes
  - Listener distribution (round-robin/geo-aware)
  - CDN integration
- **Transcoding**
  - On-the-fly format conversion
  - Multi-quality variants per mount
- **Recording/Archiving**
  - Save streams to disk
  - Export chunks (podcast/catch-up)
- **Modern Streaming**
  - WebRTC (low-latency)
  - Live video support
  - Chat / real-time metadata channels

## 🛠 Development & Maintenance
- **Language Choice**
  - C, Rust, Go, or C++
- **Extensibility**
  - Plugin system (auth, logging, codecs)
  - Script hooks (Lua, Python)
- **Testing**
  - Stress/load tests
  - Backward compatibility with Icecast tools
  - Latency and packet-loss handling
