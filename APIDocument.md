## API Documentation

### Playback
Play Sound Effect Plays a sound once. Multiple SFX can play simultaneously.
```typescript
// Plays 'assets/resources/audio/jump.mp3'
AudioManager.playSound('jump');
```

Play Music Plays a background track on loop. Automatically stops the previous music track.
```typescript
// Plays 'assets/resources/audio/bgm.mp3'
AudioManager.playMusic('bgm');
```

### Volume Control
Set Volume Accepts a float between 0.0 and 1.0.
```typescript
AudioManager.setMusicVolume(0.5); // 50%
AudioManager.setSFXVolume(1.0);   // 100%
```
Get Volume Useful for initializing UI Sliders.
```typescript
const { sfx, music } = AudioManager.getSFXAndMusicVolume();
console.log(`Music is at: ${music}`);
console.log(`SFX is at: ${sfx}`);
```
### Muting
Toggle Mute Mutes the specific channel. If unmuted, returns to the last known volume level
```typescript
AudioManager.toggleMusicMute();
AudioManager.toggleSfxMute();
```
Global Mute Mutes all audio output. Useful when the app is paused or in background.
```typescript
AudioManager.setGlobalMute(true);  // Mute all
AudioManager.setGlobalMute(false); // Restore previous state
```
### Lifecycle
Pause / Resume
```typescript
AudioManager.pauseAll();  // Pauses Music and SFX
AudioManager.resumeAll(); // Resumes Music (if it was playing)
```
## Important Notes
1. File Names: Do not include file extensions (like .mp3) when calling playSound or playMusic.

2. Web Audio Policy: On web browsers, audio context is often blocked until the user interacts with the page. Ensure your first playMusic call happens after a user interaction (like clicking a "Start" button) to avoid silence