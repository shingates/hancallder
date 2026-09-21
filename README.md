# 한콜더 · HANCALLDER

대리·배달 기사를 위한 안드로이드 앱의 **설치 페이지**입니다.

- 설치 안내: https://shingates.github.io/hancallder/
- 내려받기: [Releases](https://github.com/shingates/hancallder/releases/latest)

앱 소스는 이 저장소에 없습니다. 여기에는 설치 페이지와 배포 파일만 둡니다.

## 구조

```
index.html   설치 안내 페이지
p/           짝 연결 링크 (QR 이 가리키는 곳)
a/           앱 전달 링크
```

`p/` 와 `a/` 는 앱이 깔려 있으면 `daeridonghang://` 스킴으로 앱을 열고,
깔려 있지 않으면 내려받기 버튼을 보여 줍니다.

## 새 버전 올리기

```bash
cd ~/workspace/kkeulda/drivers
./gradlew :app:assembleRelease
gh release create v1.0.1 \
  app/build/outputs/apk/release/app-release.apk#hancallder-1.0.1.apk \
  --repo shingates/hancallder --title v1.0.1 --notes "바뀐 점"
```

서명 키는 `~/keystores/hancallder-release.jks` 에 있습니다.
**이 키를 잃어버리면 이미 깔린 앱을 업데이트할 수 없습니다.** 반드시 백업하세요.
