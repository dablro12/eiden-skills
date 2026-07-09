# eiden-skills

Codex와 Cursor에서 사용하는 개인 스킬을 백업하고 여러 PC에서 동기화하기 위한 저장소입니다.

## 구조

- `codex/skills/`: `~/.codex/skills`에 있는 Codex 스킬 백업
- `cursor/skills/`: `~/.cursor/skills`에 있는 Cursor 스킬 백업

## 복원 방법

새 PC에서 이 저장소를 받은 뒤 아래 명령으로 각 도구의 스킬 폴더에 복사할 수 있습니다.

```bash
mkdir -p ~/.codex/skills ~/.cursor/skills
rsync -a codex/skills/ ~/.codex/skills/
rsync -a cursor/skills/ ~/.cursor/skills/
```

## 백업 갱신 방법

로컬에서 스킬을 수정한 뒤에는 아래 명령으로 저장소 내용을 갱신합니다.

```bash
rsync -a ~/.codex/skills/ codex/skills/
rsync -a ~/.cursor/skills/ cursor/skills/
```
