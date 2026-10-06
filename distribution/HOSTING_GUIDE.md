# 새움마을 런처 배포 설정 가이드

## 1. GitHub 저장소 만들기

1. GitHub에 `todnaakdmf` 이름으로 새 **공개(Public)** 저장소 만들기
2. 아래 구조로 파일 업로드:

```
todnaakdmf/
├── distribution.json        ← 이 폴더의 distribution.json
├── icon.png                 ← 서버 아이콘 이미지 (선택)
└── mods/
    ├── fabric-api-0.141.3+1.21.11.jar
    ├── sodium-fabric-0.8.7+mc1.21.11.jar
    ├── iris-fabric-1.10.7+mc1.21.11.jar
    ├── journeymap-fabric-1.21.11-6.0.0-beta.65.jar
    ├── MouseTweaks-fabric-mc1.21.11-2.30.jar
    ├── punchy-2.5.8-fabric-1.21.11.jar
    ├── skinlayers3d-fabric-1.11.2-mc1.21.11.jar
    ├── DPPaintMod1.0.0.jar
    ├── DPScreenMod1.0.0.jar
    └── DP-CustomItem-Client-1.0.0.jar
```

모드 파일은 `todo/mods/` 폴더에 있습니다.

## 2. distribution.json 수정

`distribution.json` 에서 아래 항목들을 수정하세요:

### Fabric Loader 버전 설정 (완료됨)
- 버전: `0.19.5`
- MD5: `23bf6a8c5ba938db7d13959a2630357f`
- size: `1984980`

### GitHub 사용자명/저장소 (완료됨)
`https://github.com/llipp9983/todnaakdmf` 저장소 기준으로 아래처럼 이미 반영되어 있습니다:
```
https://raw.githubusercontent.com/llipp9983/todnaakdmf/main/...
```

## 3. 런처 배포 URL 업데이트 (완료됨)

`app/assets/js/distromanager.js`:
```js
exports.REMOTE_DISTRO_URL = 'https://raw.githubusercontent.com/llipp9983/todnaakdmf/main/distribution.json'
```

## 4. Minecraft 버전 확인 (완료됨)

현재 설정: `"1.21.11"`

## 완료 후 확인사항

- [ ] GitHub 저장소(`llipp9983/todnaakdmf`)가 Public인지 확인
- [ ] `distribution.json`, `icon.png`, `mods/` 전체를 저장소에 업로드
- [ ] distribution.json의 모든 URL이 실제로 접근 가능한지 확인
- [x] Fabric Loader 버전이 서버와 동일한지 확인 (0.19.5)
- [x] Minecraft 버전이 서버와 동일한지 확인 (1.21.11)
- [ ] 런처 빌드 후 테스트
