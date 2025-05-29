GitHub Actions에 워크플로우를 작성해 다음과 같이 배포가 진행되도록 합니다.

(사전작업: Ubuntu 최신 버전 설치)

1. Checkout 액션을 사용해 코드 내려받기
2. 'npm ci' 명령어로 프로젝트 의존성 설치
3. 'npm run build' 명령어로 Next.js 프로젝트 빌드
4. AWS 자격 증명 구성
5. 빌드된 파일을 S3 버킷에 동기화
6. CloudFront 캐시 무효화

## 주요 링크

- S3 버킷 웹사이트 엔드포인트: [_________](http://tjdlwns33-bucket.s3-website-ap-southeast-2.amazonaws.com)
- CloudFrount 배포 도메인 이름: d14l3cpg2sv7xn.cloudfront.net

## 주요 개념

- GitHub Actions과 CI/CD 도구: workflows/development.yml
- S3와 스토리지:
  버킷 이름: tjdlwns33-bucket
  버킷 위치(리전): ap-southeast-2
  정적 웹사이트 호스팅 설정 여부: 활성화
  저장된 주요 파일/폴더 구조: index.html, 404.html
  스토리지 용량 및 수명 주기 정책: 규칙 없음
- CloudFront와 CDN:
  배포 ID와 도메인 이름: E3DV2RVWW0N3EP / https://d14l3cpg2sv7xn.cloudfront.net
  오리진(origin)으로 연결된 S3 버킷: tjdlwns33-bucket
  캐시 정책 이름: Managed-CachingOptimized
- 캐시 무효화(Cache Invalidation): 없음
- Repository secret과 환경변수: AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY, AWS_REGION, S3_BUCKET_NAME, CLOUDFRONT_DISTRIBUTION_ID
