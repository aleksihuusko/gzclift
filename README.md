# GZCL Workout App

## 1. Project Setup

- Create the app with: `npx create-expo-app GZCLApp -t expo-template-blank-typescript`
- Set up the project structure:
  ```
  GZCLApp/
  ├── app/
  │   ├── (auth)/
  │   │   └── login.tsx
  │   ├── (tabs)/
  │   │   ├── home.tsx
  │   │   ├── profile.tsx
  │   │   └── progress.tsx
  │   ├── workout/
  │   │   ├── [tier].tsx
  │   │   └── log.tsx
  │   ├── _layout.tsx
  │   └── index.tsx
  ├── components/
  │   ├── ui/
  │   │   ├── button.tsx
  │   │   ├── input.tsx
  │   │   ├── text.tsx
  │   │   └── ...
  │   ├── exercise-card.tsx
  │   ├── workout-timer.tsx
  │   └── progress-chart.tsx
  ├── lib/
  │   ├── utils.ts
  │   ├── constants.ts
  │   └── useColorScheme.tsx
  ├── styles/
  │   └── global.css
  └── ...
  ```

## 2. Dependencies and Configuration

- Install dependencies:
  ```
  npx expo install @react-navigation/native @react-navigation/stack expo-router
  npx expo install @react-native-async-storage/async-storage expo-notifications
  npx expo install react-native-svg react-native-reanimated
  npx expo install nativewind tailwindcss
  ```
- Configure NativeWind and Tailwind CSS as per the [React Native Reusables documentation](https://rnr-docs.vercel.app/getting-started/initial-setup/#install-nativewind)
- Set up path aliases in `tsconfig.json`:
  ```json
  {
    "compilerOptions": {
      "baseUrl": ".",
      "paths": {
        "~/*": ["*"]
      }
    }
  }
  ```

## 3. Reusable Components

- Implement reusable UI components in the `components/ui/` directory:
  - Button
  - Input
  - Text
  - Card
  - Progress
  - ThemeToggle
- Create custom components:
  - ExerciseCard
  - WorkoutTimer
  - ProgressChart

## 4. Navigation and Screens

- Use Expo Router for navigation
- Implement the following screens:
  - Home: Choose workout tiers
  - Profile: User preferences and stats
  - Workout: Dynamic screen for T1, T2, T3 tiers
  - Log: Record sets, reps, and weights
  - Progress: Visualize performance over time

## 5. State Management and Data Persistence

- Use React Context for global state management
- Implement hooks for data fetching and caching with React Query
- Use AsyncStorage for local data persistence

## 6. Theming and Styling

- Implement dark mode support using NativeWind and the `useColorScheme` hook
- Use Tailwind CSS for styling components
- Configure colors in `tailwind.config.js` and `global.css`

## 7. Features Implementation

- **User Profiles**:

  - Use reusable form components for profile input
  - Store user data in AsyncStorage

- **Workout Tiers**:

  - Display exercises using FlatList with ExerciseCard components
  - Implement logging functionality with reusable Input components

- **Progress Tracking**:

  - Use react-native-svg for creating custom ProgressChart component
  - Fetch and display data from AsyncStorage

- **Timers**:

  - Create a custom WorkoutTimer component using react-native-reanimated

- **Exercise Library**:

  - Store exercise data in a local JSON file
  - Create an expandable ExerciseCard component for details

- **Calendar Integration**:

  - Use react-native-calendars for planning workouts
  - Integrate with AsyncStorage for data persistence

- **Push Notifications**:
  - Utilize expo-notifications for reminders
  - Schedule notifications based on planned workouts

## 8. Performance Optimization

- Implement code splitting and lazy loading for non-critical components
- Use React.memo and useCallback for preventing unnecessary re-renders
- Optimize images and implement lazy loading with expo-image

## 9. Testing and Error Handling

- Write unit tests using Jest and React Native Testing Library
- Implement error boundaries and proper error logging
- Use Zod for runtime validation and error handling

## 10. Accessibility and Internationalization

- Ensure high accessibility (a11y) standards using ARIA roles and native accessibility props
- Implement internationalization using react-native-localize or a similar library

## 11. Deployment and Updates

- Follow Expo's best practices for app deployment and publishing
- Implement expo-updates for over-the-air (OTA) updates

## 12. Optional Enhancements

- Implement an onboarding flow to explain the GZCL method and app usage
- Add social features like sharing progress or competing with friends

---

# GZCL Workout Plan

## Overview

The GZCL method is a flexible powerlifting program that focuses on progressive overload and customization. It's built around three tiers of exercises, each with specific intensity and volume goals.

## Tier System

1. **Tier 1 (T1)**: Main lifts

   - Intensity: 85-100% of 1RM
   - Reps per set: 1-5
   - Total reps: 10-15
   - Sets: 3-5
   - Rest: 3-5 minutes

2. **Tier 2 (T2)**: Supplemental lifts

   - Intensity: 65-85% of 1RM
   - Reps per set: 5-8
   - Total reps: 20-30
   - Sets: 3-5
   - Rest: 2-3 minutes

3. **Tier 3 (T3)**: Accessory work
   - Intensity: <65% of 1RM
   - Reps per set: 8-20+
   - Total reps: 30-50+
   - Sets: 3-5
   - Rest: 60-90 seconds

## Weekly Structure

- Frequency: 3-4 days per week
- Each workout includes exercises from all three tiers
- Focus on one main lift per workout

### Sample 4-Day Split

1. Squat Focus
2. Bench Press Focus
3. Deadlift Focus
4. Overhead Press Focus

## Exercise Selection

### Tier 1 (Main Lifts)

- Squat
- Bench Press
- Deadlift
- Overhead Press

### Tier 2 (Supplemental Lifts)

- Front Squat
- Incline Bench Press
- Romanian Deadlift
- Push Press
- Close-Grip Bench Press
- Paused Squats

### Tier 3 (Accessory Work)

- Leg Press
- Dumbbell Row
- Tricep Extensions
- Bicep Curls
- Leg Curls
- Lateral Raises
- Face Pulls

## Sample Workout Structure

### Day 1: Squat Focus

- T1: Squat (5x3 @ 85% 1RM)
- T2: Romanian Deadlift (4x6 @ 70% 1RM)
- T3a: Leg Press (3x12 @ RPE 8)
- T3b: Leg Curls (3x15 @ RPE 8)

### Day 2: Bench Press Focus

- T1: Bench Press (4x4 @ 87.5% 1RM)
- T2: Close-Grip Bench Press (3x8 @ 75% 1RM)
- T3a: Dumbbell Row (3x10 @ RPE 8)
- T3b: Tricep Extensions (3x15 @ RPE 8)

### Day 3: Deadlift Focus

- T1: Deadlift (5x2 @ 90% 1RM)
- T2: Front Squat (3x6 @ 75% 1RM)
- T3a: Pull-Ups (3xAMRAP)
- T3b: Face Pulls (3x15 @ RPE 8)

### Day 4: Overhead Press Focus

- T1: Overhead Press (4x3 @ 85% 1RM)
- T2: Incline Bench Press (3x8 @ 75% 1RM)
- T3a: Lateral Raises (3x15 @ RPE 8)
- T3b: Bicep Curls (3x12 @ RPE 8)

## Progression

1. **Linear Progression**: Increase weight by 2.5-5 lbs per week for T1 and T2 lifts.
2. **Double Progression**: For T3, increase reps (up to 20) before adding weight.
3. **Periodization**: Implement 3-week cycles, varying intensity and volume.

## Customization

1. **Experience Levels**:

   - Beginners: Start with 3 days/week, focus on form, use conservative weights
   - Intermediate: Use the standard 4-day split
   - Advanced: Add volume, incorporate variations, use more aggressive progression

2. **Goal-Specific Adjustments**:

   - Strength: Emphasize T1 lifts, use lower rep ranges
   - Hypertrophy: Add volume to T2 and T3, use higher rep ranges
   - Powerlifting: Focus on competition lifts in T1, use specific accessories

3. **Equipment Limitations**:
   - Provide alternative exercises for each tier
   - Example: Replace Barbell Bench with Dumbbell Bench or Push-Ups

## Recovery and Deload

- Implement a deload week every 4-6 weeks
- Reduce volume by 40-50% during deload weeks
- Monitor fatigue and adjust as needed

## Key App Features

1. **Workout Logging**: Track weights, sets, reps, and RPE for each exercise
2. **Progress Tracking**: Visualize strength gains and volume increases over time
3. **1RM Calculator**: Estimate one-rep max based on performance
4. **Plate Calculator**: Help users quickly determine plate loading
5. **Rest Timer**: Customizable timer for between-set rest periods
6. **Exercise Library**: Detailed descriptions and form cues for each exercise
7. **Progression Suggestions**: Recommend weight increases based on performance
8. **Customization Options**: Allow users to modify exercises, set personal goals
9. **Deload Reminders**: Notify users when it's time for a deload week
10. **Form Check**: Allow users to record and analyze their lift form

## User Onboarding

1. Assess user's experience level
2. Determine primary goals (strength, hypertrophy, powerlifting)
3. Evaluate equipment availability
4. Set initial weights based on recent 1RM or estimated max
5. Provide a brief tutorial on the GZCL method and app features

By implementing this comprehensive plan, your GZCL Workout App will provide users with a flexible, effective, and customizable strength training program.

---

# Key Notes:

1. **Customizability**: Allow the user to adjust workout days, exercises, and rest periods to fit their schedule and equipment availability.
2. **Track Progress**: Record weights lifted, sets, and reps over time to enable progressive overload.
3. **Reminder Functionality**: Encourage users to increase weight or reps every 1-2 weeks.
4. **User Feedback**: Provide tips on improving form, adjusting for injuries, and dealing with plateaus.
5. **Adaptation for Experience Levels**: Adjust intensity and volume based on user experience.
