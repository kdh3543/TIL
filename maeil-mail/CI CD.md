CI/CD는 애플리케이션 배포 과정을 자동화하여 더 짧은 주기로 고객에게 서비스를 제공하는 방식이다. 먼저, CI는 <strong>Continuous Integration의</strong> 약자로 <strong>지속적 통합</strong>을 의마한다. CD는 <strong>Continuous Delivery(지속적 전달)</strong> 또는 <strong>Continuous Deployment(지속적 배포)</strong>를 의미한다.

먼저, <strong>CI는 개발자들이 코드 변경사항을 주기적으로 메인 브랜치에 병합하는 과정을 자동화한 것이다.</strong> 이 과정에서 코드 변경사항이 발생할 때마다 자동으로 빌드와 테스트를 수행해 문제를 조기에 발견할 수 있다. 예를 들어, 여러 개발자가 함께 작업할 때 한 개발자의 변경사항이 다른 개발자의 작업과 충돌하거나 전체 애플리케이션에 문제를 일으킬 수 있는데, CI를 거치면 이러한 문제럴 병합 이전에 미리 파악할 수 있다.

<strong>CD는 CI 이후 단계를 자동화한 것으로,</strong> 애플리케이션의 변경사항을 production 환경으로 배포하는 과정을 자동화한 것이다. <strong>Continuous Delivery</strong>의 경우, <strong>배포 가능한 상태로 준비하는 과정까지는</strong> 자동화하고 실제 배포는 사람의 승인을 거쳐 수동으로 진행한다. 반면 <strong>Continuous Deployment는 production 환경에 배포하는 과정까지</strong> 모두 자동화한다.

현업에서는 GitHub Actions, Jenkins, Gitlab CI 등의 도구를 사용하여 CI/CD 파이프라인을 구축한다. 

CI/CD 프로세스에 대한 예시
- 개발자가 PR을 올리면 자동으로 테스트/빌드 실행
- 테스트/빌드를 성공한 경우 메인 브랜치로의 머지 활성화
- 메인 브랜치 머지 시 production 환경으로 자동 배포
