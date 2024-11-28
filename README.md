# GithubAction을 사용한 Blue-Green 배포 파이프라인 구성
Nginx 앱을 활용한 BlueGreen배포 테스트

## 배포 과정
1. Blue 앱이 배포되어있는 AKS 환경 (blue-deploy.yaml)
2. Green 앱 신규 배포 (green-deploy.yaml)
3. BlueApp 과 Green 앱이 함께 공존하는 시점, 이 때 관리자는 Green 앱의 정상 동작을 확인
4. 사전에 등록된 관리자에게 프로모션 승인요청 알림
5. 관리자 배포 승인시 Green 앱이 승격되어 기존의 blue-deploy.yaml로 배포되었던 버전이 삭제되고, green 버전이 새로운 Blue 버전으로 남게 됩니다.
