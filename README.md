# eiden-skills

Codex와 Cursor에서 사용하는 개인 스킬을 여러 Mac에서 안전하게 설치·백업하기 위한 저장소입니다.

## 구조

- `codex/skills/`: Codex 사용자 스킬의 원본. 설치 위치는 `~/.codex/skills/`입니다.
- `cursor/skills/`: Cursor 사용자 스킬의 원본. 설치 위치는 `~/.cursor/skills/`입니다.

각 스킬은 보통 `SKILL.md`를 포함하는 폴더입니다. Codex에서 목록에 보이는 이름을 지정하려면 `SKILL.md`의 `name`과 폴더 이름을 일치시키고, 필요한 경우 `agents/openai.yaml`의 `display_name`을 설정합니다.

## 새 Mac에서 설치하기

저장소를 받은 뒤 루트 폴더에서 실행합니다.

```bash
git clone https://github.com/dablro12/eiden-skills.git
cd eiden-skills
mkdir -p ~/.codex/skills ~/.cursor/skills
```

먼저 변경 예정 항목을 확인합니다. 이 명령은 파일을 바꾸지 않습니다.

```bash
rsync -ani --exclude '.DS_Store' codex/skills/ ~/.codex/skills/
rsync -ani --exclude '.DS_Store' cursor/skills/ ~/.cursor/skills/
```

기존 로컬 스킬을 덮어쓰지 않고, 저장소에만 있는 스킬만 설치하려면 다음을 실행합니다.

```bash
rsync -a --ignore-existing --exclude '.DS_Store' codex/skills/ ~/.codex/skills/
rsync -a --ignore-existing --exclude '.DS_Store' cursor/skills/ ~/.cursor/skills/
```

저장소 버전으로 기존 스킬까지 갱신하려면 미리보기 결과를 확인한 뒤 실행합니다.

```bash
rsync -a --exclude '.DS_Store' codex/skills/ ~/.codex/skills/
rsync -a --exclude '.DS_Store' cursor/skills/ ~/.cursor/skills/
```

설치 후 Codex를 새로 열거나 스킬 목록을 새로고침합니다. 터미널에서는 아래처럼 특정 스킬이 로드됐는지 점검할 수 있습니다.

```bash
codex debug prompt-input 'Show available skills.' | rg 'naver-review-pipeline-v2'
```

## AI 에이전트용 설치 규칙

AI 에이전트는 다음 원칙을 지켜야 합니다.

1. 설치 전 `rsync -ani`으로 변경 목록을 먼저 보여준다.
2. `--delete`를 사용하지 않는다.
3. 로컬에만 있거나 내용이 다른 스킬은 자동으로 덮어쓰지 않고, 비교 결과를 보고한 뒤 사용자 승인을 받는다.
4. `~/.codex/skills/.system`처럼 Codex가 관리하는 폴더는 이 저장소로 백업하거나 복원하지 않는다.
5. 설치 뒤에는 필요한 스킬의 `SKILL.md`와 Codex 스킬 목록 로드를 확인한다.

## 현재 Mac의 변경을 저장소에 반영하기

로컬에서 수정한 내용을 백업할 때도 먼저 차이를 확인합니다.

```bash
rsync -ani --exclude '.DS_Store' ~/.codex/skills/ codex/skills/
rsync -ani --exclude '.DS_Store' ~/.cursor/skills/ cursor/skills/
```

검토 후 선택한 스킬 폴더만 복사하고, 커밋·푸시합니다.

```bash
rsync -a --exclude '.DS_Store' ~/.codex/skills/<skill-name>/ codex/skills/<skill-name>/
git add codex/skills/<skill-name>
git commit -m "[ADD] <skill-name> 스킬 백업: 로컬 변경 반영"
git push
```
