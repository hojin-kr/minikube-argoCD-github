# minikube-argoCD-github
minikube-argoCD-github

# minikube + argoCD + github
쿠버네티스 GitHub, argoCD를 조합해서 서버 아키텍처를 구성

## 프로세스
GitHub code push
-> GitHub Action
-> Container build
-> Push to GitHub Packages
-> argoCD
-> Sync
-> deploy

## 요구사항
### Deployment 구분
- Development
- Staging
- Production

### 다양한 Deploy 방식 지원
- rolling
- blue/green
- canary

## 배포 명세 작성
[Kustomize - Kubernetes native configuration management](https://kustomize.io)

base를 기반으로 각 deployment 명세를 overay해서 사용