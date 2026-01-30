# TalkWithAGI - Technology Stack

## Project Overview

TalkWithAGI is a real-time AI voice communication platform that enables users to have natural voice conversations with AI participants alongside other human users. The platform supports web (PWA), iOS, and Android with real-time transcription and multi-language translation across 14 languages.

## Frontend - Web Application

| Technology | Version | Purpose |
|------------|---------|---------|
| Next.js | 15.1.3 | React framework with App Router and Server Actions |
| React | 19.0.0 | UI component library |
| TypeScript | 5.7.2 | Static type checking |
| TailwindCSS | 3.4.17 | Utility-first CSS framework |
| Three.js | 0.182.0 | 3D graphics library |
| React Three Fiber | 9.5.0 | React renderer for Three.js |
| React Three Drei | 10.7.7 | Three.js React helpers and abstractions |
| Lucide React | 0.468.0 | Icon library |
| clsx | 2.1.1 | Conditional CSS class utility |
| tailwind-merge | 2.6.0 | Tailwind class conflict resolution |

### 3D Visualization

Custom GLSL shaders for AI presence visualization:
- Core shader with animated displacement
- Iris shader for eye-like center effect
- Atmosphere shader for glow effects
- Bokeh shader for depth-of-field
- Grain shader for film-like texture
- Soundwave shader for audio visualization

Post-processing with Three.js EffectComposer and Unreal Bloom Pass.

## Mobile Application

| Technology | Version | Purpose |
|------------|---------|---------|
| Capacitor | 6.2.0 | Cross-platform native runtime |
| @capacitor/android | 6.2.0 | Android platform support |
| @capacitor/ios | 6.2.0 | iOS platform support |
| @capacitor/app | 6.0.2 | App lifecycle management |
| @capacitor/haptics | 6.0.2 | Haptic feedback |
| @capacitor/keyboard | 6.0.3 | Native keyboard handling |
| @capacitor/status-bar | 6.0.1 | Status bar customization |

### Android

| Technology | Version | Purpose |
|------------|---------|---------|
| Android SDK | Target 36, Min 24 | Native Android platform |
| Kotlin | 2.1.0 | Android development language |
| Gradle | 8.8.0 | Build automation |

### iOS

- Native iOS support via Xcode
- CocoaPods for dependency management

## Backend - Server

| Technology | Version | Purpose |
|------------|---------|---------|
| Node.js | 20+ | JavaScript runtime |
| Express | 4.18.2 | HTTP server framework |
| ws | 8.18.0 | WebSocket server for signaling |
| TypeScript | 5.7.2 | Static type checking |
| cors | 2.8.5 | Cross-origin resource sharing |
| dotenv | 16.3.1 | Environment configuration |
| uuid | 9.0.1 | Unique identifier generation |
| tsx | 4.6.2 | TypeScript execution |
| tsup | 8.0.1 | TypeScript bundler |

## Database & Backend Services

| Technology | Version | Purpose |
|------------|---------|---------|
| Supabase | Cloud | Backend-as-a-Service platform |
| PostgreSQL | via Supabase | Primary relational database |
| @supabase/supabase-js | 2.49.1 | Supabase client SDK |
| @supabase/ssr | 0.5.2 | Server-side rendering support |

### Database Features

- Supabase Auth for user authentication
- Supabase Realtime for live subscriptions
- Row Level Security (RLS) policies for data protection
- Database migrations for schema versioning

### Database Schema

Key tables and features:
- User profiles and authentication
- Chat rooms with short codes for sharing
- Message storage with translations
- User reports and moderation
- User blocking functionality
- Friendship system with real-time updates

## Real-Time Communication

| Technology | Version | Purpose |
|------------|---------|---------|
| mediasoup | 3.14.16 | WebRTC Selective Forwarding Unit (SFU) |
| mediasoup-client | 3.7.18 | Browser WebRTC client |
| @evan/opus | 1.0.3 | Opus audio codec encoding/decoding |
| WebRTC | Browser native | Peer-to-peer media transport |

### Supported Media Codecs

- Audio: Opus (48kHz stereo, preferred)
- Video: VP8, VP9, H.264

### Architecture

- SFU (Selective Forwarding Unit) topology for scalable multi-party calls
- WebSocket signaling for connection establishment
- DTLS/SRTP for secure media transport

## AI Integration

| Technology | Version | Purpose |
|------------|---------|---------|
| OpenAI API | 4.77.0 | AI integration SDK |
| GPT-4o Realtime API | gpt-4o-realtime-preview-2024-12-17 | Real-time speech-to-speech AI |
| OpenAI Whisper | via Realtime API | Speech-to-text transcription |
| OpenAI Chat API | via SDK | Text translation |

### AI Features

- Real-time voice conversation with AI participants
- Live speech transcription for all participants
- Automatic language detection
- Multi-language translation support

### Supported Languages (14)

English, Spanish, French, German, Italian, Portuguese, Japanese, Korean, Chinese, Arabic, Hindi, Russian, Tagalog, Vietnamese

## Monetization

| Technology | Version | Purpose |
|------------|---------|---------|
| RevenueCat Purchases Capacitor | 12.0.4 | Native in-app purchases (iOS/Android) |
| RevenueCat Purchases Capacitor UI | 12.0.4 | Paywall UI components |
| RevenueCat Purchases JS | 1.24.1 | Web subscription management |

## DevOps & Deployment

| Technology | Purpose |
|------------|---------|
| Docker | Containerization |
| Docker Compose | Multi-container orchestration |
| Railway | Cloud hosting platform (PaaS) |
| Nixpacks | Railway build system |
| Codemagic | CI/CD for mobile app builds |

### Container Configuration

- Base image: `node:20-bookworm-slim`
- Multi-stage builds for optimized images
- Separate containers for web and server

### CI/CD Pipeline (Codemagic)

- Mac Mini M2 for iOS builds
- Linux instances for Android builds
- Automated build and deployment workflows

## Build Tools & Monorepo

| Technology | Version | Purpose |
|------------|---------|---------|
| pnpm | 9.15.2 | Package manager |
| pnpm workspaces | - | Monorepo workspace management |
| Turborepo | 2.7.2 | Monorepo build orchestration |
| ESLint | 9.17.0 | Code linting |
| Prettier | 3.4.2 | Code formatting |

## Project Architecture

### Monorepo Structure

```
talkwithagi/
├── apps/
│   ├── web/          # Next.js 15 frontend (PWA)
│   ├── server/       # Node.js/Express signaling server
│   └── mobile/       # Capacitor native wrapper
└── packages/
    └── shared/       # Shared types, constants, utilities
```

### Web App (apps/web)

- Next.js 15 with App Router
- Server Components and Server Actions
- PWA with Service Worker
- Responsive mobile-first design

### Server (apps/server)

- Express HTTP server
- WebSocket signaling server
- mediasoup SFU media server
- OpenAI Realtime API integration

### Mobile (apps/mobile)

- Capacitor wrapper for web app
- Native iOS and Android builds
- Platform-specific plugins

### Shared Package (packages/shared)

- TypeScript type definitions
- Shared constants
- Utility functions

## Progressive Web App (PWA)

- Service Worker for offline support
- Web App Manifest for installability
- Standalone display mode
- iOS Add to Home Screen support
- Theme color customization

## Design Approach

- Mobile-first responsive design
- FaceTime-inspired UI/UX
- Touch-friendly interfaces (44px minimum touch targets)
- Safe area insets for notched devices
- Glass morphism visual effects

## Key Technical Features

1. **Real-time Voice AI**: Sub-second latency voice conversations with GPT-4o Realtime API
2. **WebRTC SFU Architecture**: Scalable multi-party audio/video using mediasoup
3. **Live Transcription**: Real-time speech-to-text for all participants
4. **Multi-language Translation**: Automatic translation across 14 languages
5. **3D AI Visualization**: Custom GLSL shaders for dynamic AI presence rendering
6. **Cross-platform**: Single codebase for Web, iOS, and Android
7. **Monorepo Architecture**: Shared code and types across all applications
8. **Real-time Database**: Supabase Realtime for live data synchronization
