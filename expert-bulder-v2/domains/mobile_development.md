# Domain: Mobile Development

## Recommended Stack

| Layer | Tool | Why |
|---|---|---|
| Cross-platform | React Native | One codebase, iOS + Android |
| Native Android | Kotlin | Modern, officially recommended |
| Native iOS | Swift | Standard for iOS |
| Backend | FastAPI / Firebase | FastAPI for custom, Firebase for quick auth/DB |
| State management | Redux / Zustand (RN) | Redux mature, Zustand simpler |

## Best Practices

- Design for touch first — minimum tap target 44x44px
- Handle offline state — mobile users lose connectivity
- Never store sensitive data in AsyncStorage unencrypted
- Test on real devices, not just simulators
- Handle different screen sizes explicitly
- Minimize app size — users uninstall large apps
