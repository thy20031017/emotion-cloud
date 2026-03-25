# 情绪云 - 轻量AI情绪陪伴与可视化系统

## 1. Project Overview

- **Project Name**: 情绪云 (Emotion Cloud)
- **Project Type**: Single Page Web Application
- **Core Functionality**: AI emotion companion with cloud visualization, emotion tracking, and light social connection
- **Target Users**: College students seeking emotional wellness support

## 2. UI/UX Specification

### Layout Structure

**Main Navigation (Bottom on mobile, Left sidebar on PC)**
- Home (情绪云)
- Dashboard (数据面板)
- Timeline (情绪追踪)
- Memory Jar (能量罐)
- Friends (密友)
- Profile (我的)

**Page Sections**
- Header: App title + date/time + settings icon
- Main Content: Dynamic based on selected tab
- Bottom Nav: Mobile navigation bar

### Responsive Breakpoints
- Mobile: < 768px (bottom navigation)
- Tablet: 768px - 1024px
- Desktop: > 1024px (left sidebar + main content)

### Visual Design

**Color Palette**
- Primary Background: #F8FAFC (soft white)
- Secondary Background: #F1F5F9 (light gray)
- Cloud Base: #E2E8F0
- Calm Blue: #7DD3FC (平静)
- Warm Orange: #FDBA74 (开心)
- Sad Red: #FCA5A5 (低落)
- Anxious Purple: #C4B5FD (焦虑)
- Gold Accent: #FCD34D (安慰金光)
- Text Primary: #1E293B
- Text Secondary: #64748B

**Typography**
- Font Family: "Noto Sans SC", "Nunito", sans-serif
- Headings: 600 weight, 1.5rem - 2rem
- Body: 400 weight, 0.875rem - 1rem
- Numbers: "DM Sans", monospace

**Spacing System**
- Base unit: 4px
- Small: 8px
- Medium: 16px
- Large: 24px
- XL: 32px

**Visual Effects**
- Cloud: Soft blur shadows, floating animation (3-5s ease-in-out)
- Rain animation: Dashed lines falling with fade
- Golden light: Radial gradient pulse effect
- Cards: Rounded corners (16px), subtle shadows
- Transitions: 0.3s ease for all interactions

### Components

**Cloud Component**
- SVG-based cloud shape
- Dynamic fill color based on emotion
- States: normal, clicked (pulse animation), raining
- Touch/click interaction with ripple effect

**Data Cards**
- Glassmorphism style with backdrop blur
- Icon + value + label layout
- Subtle gradient borders

**Charts**
- Smooth curve line charts
- Gradient fills under lines
- Animated data points

**Memory Cards**
- Polaroid-style design
- Image placeholder + text
- Date stamp

**Friend Cloud**
- Smaller cloud representation
- Rain overlay when sad
- Golden glow when receiving comfort

## 3. Functionality Specification

### Core Features

**1. Emotion Cloud Homepage**
- Central interactive cloud (SVG animation)
- Color changes based on emotion state:
  - Calm: #7DD3FC (淡蓝)
  - Happy: #FDBA74 (暖橙)
  - Sad: #FCA5A5 (低落红)
  - Anxious: #C4B5FD (焦虑灰紫)
  - Neutral: #E2E8F0 (云白)
- "拍一拍" interaction: click/tap triggers:
  - Color softening animation (1s)
  - Gentle pulse effect
  - Particle burst animation
  - Auto-revert after 3s

**2. Emotion Data Panel**
- Pressure gauge (0-100): Circular progress with gradient
- Emotion valence: -1 to +1 scale display
- Arousal level: 0-100 scale
- Daily emotion trajectory: Line chart (hourly)
- Quick emotion input buttons

**3. Long-term Tracking**
- Weekly view: 7-day emotion bars
- Monthly calendar: Color-coded days
- Trend chart: Smooth line over time
- Peak hours annotation
- Statistics summary

**4. Memory Jar (能量罐)**
- Add new memory: Title + description + optional mood
- Memory cards display in masonry grid
- Filter by date range
- Memory count display
- Tap to view full memory

**5. Emotion Warning System**
- Pressure threshold: 70 (warning), 85 (alert)
- Progressive notifications:
  - Level 1: Gentle reminder ("今天有点累了呢")
  - Level 2: Suggestion ("要不要听首歌?")
  - Level 3: Warm prompt ("记得照顾好自己")
- Dismissible with snooze option

**6. Social Light Connection**
- Mock friend list (local simulation)
- Friend's cloud status display
- Rain animation when friend is sad
- "拍一拍" sends golden light to friend
- No text, pure visual comfort

**7. Personal Center**
- User avatar (placeholder)
- Username & bio
- Total days tracked
- Emotion statistics
- Settings:
  - Wearable device simulation toggle
  - Notification preferences
  - Data export (JSON)
  - Clear data option

### Data Handling
- All data stored in localStorage
- Data structure:
  ```json
  {
    "emotions": [...],
    "memories": [...],
    "friends": [...],
    "settings": {...}
  }
  ```
- Auto-save on changes
- Data export/import support

### Wearable Device Simulation
- Input panel (toggle in settings)
- Manual input fields:
  - Heart Rate (60-120 bpm)
  - HRV (20-100 ms)
  - Stress Value (0-100)
- Simulated data generation option

## 4. Acceptance Criteria

### Visual Checkpoints
- [ ] Cloud animates smoothly and responds to clicks
- [ ] Colors transition naturally between emotion states
- [ ] Rain animation plays when viewing sad friend
- [ ] Golden light effect visible when sending comfort
- [ ] All charts render with animations
- [ ] Responsive layout works on mobile and desktop
- [ ] Memory jar displays cards in grid layout

### Functional Checkpoints
- [ ] Emotion state persists after page refresh
- [ ] New memories can be added and displayed
- [ ] Warning notifications appear at thresholds
- [ ] Friend status updates reflect in UI
- [ ] Settings toggle work correctly
- [ ] Data can be exported and cleared

### Performance
- [ ] Initial load < 3 seconds
- [ ] Animations run at 60fps
- [ ] No console errors
- [ ] Works offline (localStorage)
