# 생성형 AI 사용 기록

이 과제에서 생성형 AI(ChatGPT, Claude, Gemini, Copilot 등)를 쓸 때마다 아래 표에 **한 줄씩** 추가할 것.

- **날짜**: 사용한 날 (YYYY-MM-DD)
- **도구**: 사용한 AI 도구 이름
- **관련 기능**: F1–F5 중 무엇 (Git 사용법·README 등 기능과 무관하면 `기타`)
- **무엇을 물었나**: 질문·요청 내용을 구체적으로 (예: "pygame 에서 사각형 충돌을 확인하는 함수")
- **결과를 어떻게 반영/수정했나**: 받은 답을 그대로 썼는지, 어디를 고쳤는지, 쓰지 않았다면 왜인지

AI 를 전혀 쓰지 않았다면 표를 지우고 "이 과제에서 생성형 AI 를 사용하지 않았습니다." 라고 적을 것.
아래 `예시` 줄은 지우고 제출할 것.

| 날짜 | 도구 | 관련 기능 | 무엇을 물었나 | 결과를 어떻게 반영/수정했나 |
|---|---|---|---|---|
| 2026-11-18 | Gemini | 기타 | 전체 Git 작업 일정 구성 | 4일(수~토) 분할 브랜치·병합 워크플로우를 적용 |
| 2026-11-18 | Gemini | 기타 | Windows VS Code 터미널에서 `pip`와 `python` 명령어가 인식되지 않을 때 `pygame` 설치 및 실행 방법 | `py -m pip install pygame` 및 `py main.py` 실행 안내를 반영하여 개발 환경 구성 및 테스트 완료 |
| 2026-11-18 | Gemini | F1 | `entities.py`의 `Player.update()` 좌우 방향키 이동 및 화면 경계 이탈 방지 로직 구현 방법 | `pygame.key.get_pressed()`와 `self.rect.left`/`right` 경계 제한 코드를 반영하고 `feature/move` 브랜치에서 커밋 |
| 2026-11-19 | Gemini | F2 | 플레이어 상단에서 총알을 생성해 위로 이동·화면 이탈 시 제거하는 방법 | `Player.shoot()`에서 `Bullet(self.rect.centerx, self.rect.top)`을 생성하고 `Bullet.update()`에서 `BULLET_SPEED`만큼 이동 후 `self.rect.bottom < 0`일 때 `self.kill()`로 제거하도록 반영했으며, `main.py`에서 `not self.game_over` 조건을 함께 적용함 |
| 2026-11-20 | Gemini | F3 | 상단 HUD 표시 방법 | 좌측 상단 `SCORE` 표시를 `draw()`에 반영 |
| 2026-11-20 | Gemini | F4 | 플레이어 피격 및 적 하단 통과 시 생명 감소, 게임 오버 화면 중앙 텍스트 배치 좌표 | 피격·통과 생명 차감 로직을 반영하고, 음수 생명 표시 방지를 위해 `self.lives <= 0`일 때 `0`으로 고정하도록 적용 |
| 2026-11-21 | Gemini | F5 | `highscore.txt` 파일 입출력 예외 처리 방법 | `FileNotFoundError`/`ValueError` 예외 처리와 로컬 점수 파일 제외를 위해 `.gitignore`에 추가 |
| 2026-11-21 | Gemini | 기타 | 원격 브랜치 푸시(`feature/restart`), `README.md` 체크리스트 및 `AI_USAGE.md` 작성법 | 누락된 `feature/restart` 원격 푸시 완료 후 `README.md`와 `AI_USAGE.md` 최종 정리 |