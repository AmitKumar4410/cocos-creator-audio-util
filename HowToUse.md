## How to Use
### 1. Editor Setup (Cocos Creator)

1. Open your **Main Scene** (or a persistent "Loading" scene).
2. Create an **Empty Node** named `AudioController`.
3. Add **Two** `AudioSource` components to this Node:
   - **Source 1 (SFX):** Uncheck "Play On Awake", Uncheck "Loop".
   - **Source 2 (Music):** Uncheck "Play On Awake", Check "Loop".
4. Reference these sources in your main entry script (see below).

Scene
 ├── AudioController (PersistNode)
 │    ├── sfx (Node with AudioSource)
 │    └── music (Node with AudioSource)

### 2. Folder Structure

The AudioManager relies on `resources.load`. Ensure your audio files are located inside a `resources` folder.

```text
assets/
  ├── resources/
  │    ├── audio/          <-- Default folder name (configurable)
  │    │    ├── bgm.mp3
  │    │    ├── jump.wav
  │    │    └── click.mp3

```
### Initialization
In your main entry script (e.g., GameManager.ts or HomeScene.ts), import the manager and initialize it in onLoad.

```typescript
import { _decorator, Component, AudioSource } from 'cc';
import { AudioManager } from './utils/AudioManager';

const { ccclass, property } = _decorator;

@ccclass('GameManager')
export class GameManager extends Component {

    @property(Node)
    public audioController: Node = null!;

    @property(AudioSource)
    public sfxSource: AudioSource = null!;

    @property(AudioSource)
    public musicSource: AudioSource = null!;

    onLoad() {
        // Initialize the Audio Manager
        // AudioManager.init(sfxSource, musicSource, folderPath?, storageKey?)
        AudioManager.init(
            this.sfxSource, 
            this.musicSource, 
            'audio',                 // Folder path inside assets/resources/
            'game-audio-settings'    // LocalStorage key
        );

        // Optional: Play music immediately
        AudioManager.playMusic('bgm'); 
        director.addPersistRootNode(audioController); // Very Important
       }
}
```