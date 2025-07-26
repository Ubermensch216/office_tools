# 문짝 (Moon-jjak)

"문서를 짝 맞춰준다"는 의미의 **문짝**은 완전한 오프라인 환경에서 동작하는 문서 병합/분할 웹 애플리케이션입니다.
별도의 서버나 프로그램 설치 없이, 단일 HTML 파일을 웹 브라우저에서 여는 것만으로 PDF, DOCX, XLSX, TXT 파일의 병합과 분할 작업을 안전하고 빠르게 처리할 수 있습니다.

## 주요 기능

- **완전한 오프라인 동작**: 모든 기능은 사용자의 브라우저 내에서만 실행되며, 파일이 외부 서버로 전송되지 않아 민감한 문서도 안전하게 처리할 수 있습니다.
- **다양한 파일 포맷 지원**:
  - **PDF**: 페이지 단위 병합 및 분할
  - **DOCX (Word)**: 파일 단위 병합
  - **XLSX (Excel)**: 시트 단위 병합
  - **TXT**: 파일 단위 병합
- **직관적인 UI**: 파일 선택, 분석, 옵션 설정, 미리보기, 다운로드 등 모든 과정을 손쉽게 진행할 수 있습니다.

## 기술 구조

- **Single-File HTML**: 모든 HTML, CSS, JavaScript 코드가 단일 `index.html` 파일에 포함되어 있어 배포와 사용이 간편합니다.
- **Front-end Only**: 백엔드 서버 없이 순수 JavaScript와 웹 API만을 사용하여 구현되었습니다.
- **오픈소스 라이브러리**: 검증된 오픈소스 라이브러리를 사용하여 핵심 기능을 구현했습니다.

## 사용된 라이브러리 및 라이선스

| 라이브러리 | 용도 | 라이선스 |
|---|---|---|
| [pdf-lib.js](https://pdf-lib.js.org/) | PDF 생성, 수정, 병합, 분할 | MIT License |
| [SheetJS (xlsx.js)](https://sheetjs.com/) | XLSX (Excel) 파일 파싱 및 생성 | Apache 2.0 License |
| [mammoth.js](https://github.com/mwilliamson/mammoth.js) | DOCX (Word) to HTML 변환 (미리보기용) | BSD-2-Clause License |
| [JSZip](https://stuk.github.io/jszip/) | DOCX 파일 구조(zip) 처리 | MIT License or GPLv3 |
| [FileSaver.js](https://github.com/eligrey/FileSaver.js/) | 브라우저에서 파일 저장 | MIT License |
| [Bootstrap](https://getbootstrap.com/) | UI 프레임워크 | MIT License |

## 브라우저 지원

본 애플리케이션은 다음의 최신 버전 웹 브라우저에서 가장 잘 동작합니다:

- Chrome
- Firefox
- Safari
- Edge

*Internet Explorer는 지원하지 않습니다.*
