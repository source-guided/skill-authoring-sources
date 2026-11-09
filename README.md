# 스킬 제작 원천

`project-builder`에서 필요할 때 선택해 연결하는 독립 원천입니다. 기본 설치에 포함되지 않으며 다른 원천을 미리 다운로드하지 않습니다.

진입 색인은 `references/index.json`입니다. 원격 색인 주소를 연결하거나 이 저장소를 로컬로 받아 같은 색인 경로를 연결할 수 있습니다. 내부 스킬은 원천 안에서만 사용하고 전역 스킬로 설치하지 않습니다.

내용과 변경 규칙은 이 저장소의 `AGENTS.md`가 소유합니다. 소스 정보는 `source.json`, 공개 파일 목록은 `source-files.json`에 있습니다.

## 원천 검증

선택한 참조 클라이언트 체크아웃의 경로를 `client_root`로 지정해 실행합니다. 검증을 위해 다른 원천을 설치하지 않습니다.

```sh
client_root=/path/to/project-builder
python3 "$client_root/scripts/validate_source.py" --source .
PYTHONPATH="$client_root/plugins/project-builder/scripts" python3 -m unittest discover -s tests -p 'test_*.py' -v
```

참여 계약 검사와 별도로 대표 한글·영문 질문이 관련 원천을 첫 다섯 검색 결과에서 찾고 후속 주소를 해석하는지 확인합니다. 이 검사는 지침을 적용한 모델의 판단 품질이나 제품 수용 여부를 증명하지 않습니다. 지침의 판단 방식이 바뀌면 원천 소유의 대표 작업으로 결과를 별도 검토합니다.
