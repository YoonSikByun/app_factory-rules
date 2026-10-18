# 공개 배포 파일 (GitHub Pages 대상)

- `costcalc/platform-fees.json`: CostCalc 원격 요율 파일. 앱이 하루 1회 받아 번들보다 `checkedOn`이 새로우면 교체한다 (RemoteRuleUpdater).
- 갱신 절차: `scripts/rules/watch-fee-pages.py`로 변경을 확인 → 공식 페이지 원문 대조 → `Apps/CostCalc/CostCalc/Resources/platform-fees.json`과 이 파일을 **같이** 갱신(checkedOn 오늘 날짜) → docs/apps/costcalc/research/fees.md 기록 → push.
- 배포: 이 폴더를 공개 저장소 `app_factory-rules`(GitHub Pages)로 복사한다. 주소는 `RemoteRuleUpdater.remoteURL`. 저장소가 아직 없으면 앱은 조용히 번들 값을 쓴다.
- 안전장치: 스키마 버전·판매처 id 집합·요율 범위 검사, 확인일이 새롭지 않으면 무시, 200KB 초과 무시, 네트워크 실패 무시.
