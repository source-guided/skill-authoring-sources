# 스킬 제작 원천

이 저장소는 스킬 제작의 내용·기준·예제·검증을 소유한다. [참조 진입점](references/index.json)에서 현재 작업에 필요한 내부 capability와 workflow를 찾아 적용한다.

공통 참조 절차는 사용 중인 참조 클라이언트의 `usage` / `entry`, 참여 경계는 `usage` / `source-contract`를 따른다. 이 원천의 참조 진입점에도 `client-entry`, `client-contract` 경로가 있다. 다른 역할이 필요하면 소비자가 선택한 연결로 돌아간다.

제작 방법 변경은 현재 선택된 제작 원천을 참조한다. 변경 후 참조 클라이언트의 `scripts/validate_source.py --source <이 저장소>`와 변경에 맞는 소유 도메인 검사를 실행한다.
