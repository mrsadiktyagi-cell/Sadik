# Budgeting & Savings Tag Feature

## Overview
Add a budgeting/savings tag system that allows users to mark notes as "saving goal" with a target amount and track progress.

## Feature Specification

### 1. **Tag System**
- Users can create and assign "saving goal" tags to notes
- Each tag includes:
  - Tag name (default: "Saving Goal")
  - Target amount (currency)
  - Current amount (tracked)
  - Progress percentage
  - Description/notes

### 2. **User Interface**
- **Tag Creation Modal**: Input target amount, description
- **Note Tagging**: Ability to mark/unmark notes as savings goals
- **Goal Dashboard**: 
  - List all active saving goals
  - Show progress bars (current vs target)
  - Sort by progress, amount, or date created
- **Goal Details Page**: View full details, update amounts, edit description

### 3. **Functionality**
- Create multiple saving goals
- Update current savings amount
- Track progress visually
- Filter notes by goal
- Archive/delete goals
- Local storage (mobile) or cloud sync (backend)

### 4. **Data Model**
```
SavingGoal {
  id: UUID
  name: String
  targetAmount: Double
  currentAmount: Double
  currency: String (USD, INR, etc)
  description: String
  createdAt: DateTime
  updatedAt: DateTime
  status: "active" | "archived" | "completed"
  linkedNotes: Array<NoteID>
}
```

## Development Phases

### Phase 1: MVP (Core Feature)
- [ ] Create UI components for savings goal tag
- [ ] Implement local storage (SQLite/Realm)
- [ ] Build goal creation & editing screens
- [ ] Add progress tracking visualization
- [ ] Estimated: 2-3 weeks

### Phase 2: Enhancement
- [ ] Cloud sync (Firebase/Backend API)
- [ ] Goal notifications & reminders
- [ ] Export/reports functionality
- [ ] Estimated: 1-2 weeks

### Phase 3: App Store Release
- [ ] TestFlight (iOS) & Play Store Beta testing
- [ ] Build & release workflows (GitHub Actions)
- [ ] App Store & Play Store submissions
- [ ] Estimated: 1 week

## Tech Stack Recommendations

### Option A: Flutter (Recommended - Cross-platform)
- **Advantages**: Single codebase for iOS & Android, faster deployment
- **Stack**: Flutter + Firebase Firestore + GitHub Actions
- **Timeline**: 4-6 weeks total

### Option B: React Native
- **Advantages**: JavaScript ecosystem, code sharing
- **Stack**: React Native + Firebase + GitHub Actions
- **Timeline**: 5-7 weeks total

### Option C: Native (iOS + Android separate)
- **Advantages**: Best performance, full platform access
- **Stack**: Swift (iOS) + Kotlin (Android) + Backend API
- **Timeline**: 8-12 weeks total

## Deployment to App Stores

### App Store (iOS)
- [ ] Apple Developer Account ($99/year)
- [ ] Xcode build & code signing
- [ ] TestFlight beta testing
- [ ] Submit for review (typically 1-2 days)

### Play Store (Android)
- [ ] Google Play Developer Account ($25 one-time)
- [ ] Android build signing
- [ ] Internal testing & staged rollout
- [ ] Submit for review (typically 2-3 hours)

## CI/CD Pipeline
```yaml
GitHub Actions Workflows:
1. build.yml - Build APK/IPA on every push
2. test.yml - Run unit & widget tests
3. release.yml - Build & submit to app stores
```

## Success Criteria
- ✅ Feature works offline (local storage)
- ✅ Smooth UI/UX with proper progress visualization
- ✅ Both iOS & Android builds pass app store review
- ✅ Beta testing with 10+ users before launch
- ✅ Analytics tracking for feature usage

## Next Steps
1. Choose tech stack (Flutter recommended)
2. Set up project structure & dependencies
3. Begin Phase 1 development
4. Create GitHub Actions workflow for builds
5. Set up TestFlight & Play Store beta programs
