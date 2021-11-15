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

base를 기반으로 각 deployment 명세를 overay해서 사용합니다.
각 Deployment별로 특성에 따라 replicaset, resources를 overay하여 사용합니다.

argoCD에서 path별로 구분하여 직관적으로 Deployment를 구분하여 배포를 수행합니다.

![image](https://user-images.githubusercontent.com/22079767/141793170-5efad450-5718-4eba-a201-2cbabeb1730d.png)


![image](https://user-images.githubusercontent.com/22079767/141792913-ce9d00a7-ca4f-4fef-b0c1-c785c6fc05a0.png)

![image](https://user-images.githubusercontent.com/22079767/141792992-e0e007ab-942a-4550-979d-6c1c40ae96de.png)
![image](https://user-images.githubusercontent.com/22079767/141793016-86dd3415-5baf-4408-8ba9-8ed5dcaf90ae.png)
