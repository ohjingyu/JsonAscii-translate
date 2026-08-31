<div align="center">

# 🛠️ JsonAscii-translate

**JSON · ASCII · 진수 · URL · QR · Unicode · Base64 · 인코딩 — 개발자용 텍스트/데이터 변환기**

빌드 과정도, 서버도, 설치도 없습니다. `index.html` 파일 하나를 열면 모든 변환 작업이 브라우저 안에서 끝납니다.

![No build step](https://img.shields.io/badge/build-none-6fb08a?style=flat-square)
![Single file](https://img.shields.io/badge/deploy-single%20HTML%20file-d7a63f?style=flat-square)
![Vanilla JS](https://img.shields.io/badge/stack-vanilla%20JS-dd6f61?style=flat-square)
![Runs offline](https://img.shields.io/badge/network-외부%20전송%20없음-8a8d94?style=flat-square)

</div>

---

## 왜 만들었나

JSON 정렬, Base64 변환, 진수 계산처럼 자잘하지만 자주 필요한 개발 작업을 매번 다른 사이트를 돌아다니며 처리하기 귀찮아서 만든 도구입니다. 입력한 데이터는 서버로 전송되지 않고 전부 브라우저 안에서만 처리됩니다.

## 기능

| 도구 | 할 수 있는 것 |
|---|---|
| **JSON** | 정렬(Pretty) / 압축(Minify) · 문자열 인코딩 · 문자열 디코딩 — 세 작업이 각각 독립된 입력/결과 박스로 분리되어 있어 원본을 건드리지 않고 바로 비교할 수 있습니다. |
| **ASCII** | 텍스트 ↔ 코드 실시간 변환. 코드 입력 시 10진수·16진수(`0x`)·2진수(`0b`)를 자동으로 구분해서 인식합니다. 0–127 전체 표를 문자/코드/이름으로 검색할 수 있습니다. |
| **진수 변환** | 2 / 8 / 10 / 16진수를 입력하는 즉시 서로 변환합니다. BigInt를 사용해 자릿수 제한 없이 큰 수도 정확하게 계산합니다. 문자열을 넣으면 각 문자의 코드를 진수별로 한 번에 나열해줍니다. |
| **URL** | `encodeURIComponent` / `encodeURI` / `decodeURIComponent`을 각각 버튼으로 구분해서 실행하고, 결과와 함께 URL을 프로토콜·호스트·경로·쿼리로 나눠 보여주는 파서를 제공합니다. |
| **QR 코드** | 텍스트나 URL을 QR 코드로 생성해 PNG로 다운로드합니다. 반대로 QR 이미지를 드래그·붙여넣기·파일 선택으로 올리면 내용을 디코딩합니다. |
| **Unicode** | 문자를 UTF-16(`\uXXXX`) / ES6(`\u{XXXX}`) / HTML(`&#XXX;`) / UTF-8 바이트 형식으로 변환하고, 반대 방향 변환도 지원합니다. 문자 하나하나의 코드포인트·바이트 구성을 상세표로 확인할 수 있습니다. |
| **Base64** | 텍스트 인코딩과 디코딩이 각각 독립된 박스로 분리되어 있습니다. 인코딩 시 URL-safe(`+`→`-`, `/`→`_`, 패딩 제거) 옵션을 체크박스 하나로 켤 수 있고, 디코딩은 표준·URL-safe 형식을 자동으로 함께 인식합니다. |
| **ANSI ↔ UTF-8** | 한국어(EUC-KR/CP949), 일본어(Shift_JIS 등), 중국어(GBK/Big5 등) 코드페이지를 UTF-8과 상호 변환합니다. 깨진 글자(Mojibake)를 붙여넣으면 가능한 인코딩 조합을 자동으로 추측해 복구 후보를 점수순으로 보여줍니다. |

## 시작하기

별도 설치가 필요 없습니다.

```bash
git clone https://github.com/ohjingyu/JsonAscii-translate.git
cd JsonAscii-translate
open index.html   # 또는 브라우저에서 파일을 직접 드래그해서 열기
```

정적 호스팅에 그대로 올려도 동작합니다 (Cloudflare Pages, GitHub Pages, Vercel 등).

## 기술 스택

- 순수 HTML / CSS / JavaScript — 프레임워크, 번들러, `node_modules` 없음
- [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) — QR 코드 생성
- [jsQR](https://github.com/cozmo/jsQR) — 이미지에서 QR 코드 디코딩
- [text-encoding](https://github.com/inexorabletash/text-encoding) — 레거시 코드페이지(EUC-KR, Shift_JIS 등) 인코딩
- [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) / [Inter](https://fonts.google.com/specimen/Inter) — 서체

## 라이선스

별도 명시가 없는 한 개인 용도로 자유롭게 사용·수정하세요.
