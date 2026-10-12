# hwp

HWP/HWPX 문서 작업용 Claude Code 프로젝트입니다. [NomaDamas/k-skill](https://github.com/NomaDamas/k-skill)의 **🛠️ 개발자·문서 도구** 스킬을 프로젝트 스코프(`.claude/skills/`)로 설치해 두었습니다.

## 포함된 스킬

| 스킬 | 할 수 있는 일 | 필요 환경 |
| --- | --- | --- |
| [`hwp`](.claude/skills/hwp/instruction.md) | `.hwp/.hwpx` → Markdown/JSON 변환, 문서 비교, 양식 필드 추출, Markdown→HWPX 역변환 (kordoc 기반, 읽기·변환 전용) | Node.js 18+ |
| [`rhwp-edit`](.claude/skills/rhwp-edit/instruction.md) | `.hwp` 본문 텍스트 삽입/삭제, replace-all, 표 생성, 셀 수정 (`k-skill-rhwp` CLI) | Node.js 18+ |
| [`rhwp-advanced`](.claude/skills/rhwp-advanced/instruction.md) | 레이아웃 디버깅, IR 덤프, `ir-diff`, 썸네일 추출, 배포용 문서 잠금 해제 (업스트림 `rhwp` CLI) | `rhwp` 바이너리 (`cargo install rhwp`) |
| [`kr-whois-lookup`](.claude/skills/kr-whois-lookup/instruction.md) | `.kr`/`.한국` 도메인·IP·AS 공개 WHOIS 조회 (k-skill-proxy 경유) | 인터넷, `curl` |

각 스킬 폴더에는 `SKILL.md`(Claude Code가 읽는 진입점), `instruction.md`(전체 사용 안내), `skill.json`이 있습니다.

## 사용 방법

1. 이 저장소를 클론하고 해당 폴더에서 Claude Code를 실행합니다.
2. `/hwp`, `/rhwp-edit` 등으로 직접 호출하거나, "이 HWP를 Markdown으로 바꿔줘"처럼 요청하면 스킬이 자동으로 선택됩니다.
3. HWP 스킬을 쓰려면 [Node.js 18+](https://nodejs.org/)를 먼저 설치하세요.

## 스킬 업데이트

Node.js 설치 후 공식 설치 도구로 최신 버전을 받을 수 있습니다 (`-g` 없이 실행하면 프로젝트 스코프에 설치).

```bash
npx --yes skills add NomaDamas/k-skill --skill hwp --skill rhwp-edit --skill rhwp-advanced --skill kr-whois-lookup
```

## 출처 및 라이선스

스킬 파일은 [NomaDamas/k-skill](https://github.com/NomaDamas/k-skill) 커밋 `50d7bb3`에서 수정 없이 복사했으며, MIT 라이선스를 따릅니다 ([`LICENSE-k-skill`](.claude/skills/LICENSE-k-skill)).
