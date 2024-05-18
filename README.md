# GameDay & Jam Strategy

# Early Game

- **Briefing, Runbook**을 토대로 **task definition** & **prioritizing** 수행
    - GameDay의 경우 traffic을 처리하기 위한 **initial infra**를 고려
    - GameDay의 경우 각 task 간의 dependency를 파악
    - Jam의 경우 **long-running**(CI/CD pipeline, ML)을 고려
    - Jam의 경우 첫 문제를 easy로 선택할 것

# Mid Game

- 문제 풀이의 각 step에 충분한 시간을 두며 진행할 것.
    - 채점 방식에 따라 설정 값 전파, CloudWatch metric 집계 등에 시간이 걸릴 수 있음
    - 오답을 제출하지 않게 formatting 더블 체크
- 풀이하는 데에 10분 이상 걸리는 문제는 **히스토리를 기록**하고 다른 문제로 넘어갈 것
    - Lambda code, IAM policy 작성
- Application의 **각 계층 별로 monitoring** 가능하도록 구성
    - GameDay Dashboard & Event Log를 중점으로 확인
    - CloudFront > ALB > Application > Database의 핵심 지표를 모아 대시보드 구성
        - Request count, Error rate, Duration
        - Network In/Out Usage
        - (Application & Database) CPU, Memory Usage & Health check status
- 다른 선수의 풀이 현황과 나의 풀이 현황을 참고하여 문제 자체 오류인지 판단

# Late Game

- 추가 득점을 노리는 대신 실점을 막기 위한 작업을 수행
    - GameDay의 경우 각 service의 best practice 구현
    - Jam의 경우 clue를 써서 남은 문제를 모두 해결
- 작업 내역서, 생성한 리소스 설명 작성

# Common Issues

- 심리적 압박 or 특정 생각에 갇힌 상태에서 문제 지문을 정확하게 읽지 않음
    - 주의를 다른 곳으로 돌려서 환기를 시킬 필요가 있음
        - 창 밖 쳐다보기
        - 주변의 사물이나 공간 분석하기. 달력과 같이 복잡한 사물일 수록 좋음
    - 한가지 방법으로 삽질 하는 것보다 5분의 휴식을 가지는 것이 더 도움이 됨
- 구성된 AWS resource에 chaos가 발생했을 때 감지가 느림
    - 발생한 문제의 원인을 정확히 파악하는 연습이 필요.
    - 감으로 추측하지 않고, 정확한 근거(오류 메시지, 로그, 메트릭)을 기반으로 원인을 파악해야 함
- Lambda function을 작성하는 경우 적절한 테스트가 어려움
    - Lambda handler에 주입되는 event의 schema를 잘 모름
    - Lambda document에서 가장 많이 쓰이는 case는 확인 가능
    - https://docs.aws.amazon.com/lambda/latest/dg/lambda-services.html
- 리소스(network, IAM permission)를 마지막에 변경하여 재부팅이나 app 재시작 시 제대로 동작하지 않음
    - 리소스 변경 후 무조건 app을 새롭게 rollout 해주어 정상 동작하는지 확인
    - 리소스 변경은 경기 종료 30분 이전에는 모두 완료할 것