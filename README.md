# 김재후 (Kim Jaehoo)

<div align="center">
  
  ## 🚀 Dev Ops / ML Ops / SRE / Back-End Dev
  
  [![Email](https://img.shields.io/badge/Email-nkimtnt%40gmail.com-blue?style=flat-square&logo=gmail)](mailto:nkimtnt@gmail.com)
  [![Website](https://img.shields.io/badge/Website-kimvayne.xyz-orange?style=flat-square&logo=firefox)](https://kimvayne.xyz)
  [![Project](https://img.shields.io/badge/Project-moolmeow.com-red?style=flat-square&logo=github)](https://moolmeow.com)

</div>

---

## 💡 Professional Profile

> 개발은 결국 내가 원하는 것을 만드는 행위.  
> 나는 혼자서 모든 서비스를 구성해보고 싶어. 왜? 전체를 보는 눈이 있는게 실력이라고 생각하거든.  
> 그래서 진짜로 혼자 한다.  

맥미니를 활용해 집에서 물뮤(moolmeow) 서비스를 혼자 만든다.

```mermaid
graph LR
    A[Cloudflare] --> B[Vercel]
    B --> C[Nextjs]
    C --> D[Mikrotic Router]
    D --> E[Mac mini]
    E --> F[Virtual Box VM]
    F --> G[Kubernetes]
    G --> H[Pods]
```

이 모든 과정을 이해하고 구현할 수 있으면 어떤 트러블도 슈팅 가능하고 무엇이든 해결 못할까.  
추후에는 Flutter를 사용하여 앱 제작 + ML/DL로 사용자 맞춤 콘텐츠 제작 계획.  
이 모든 것을 혼자서 할 수 있을까? → 일단 해봐! → [kimvayne.xyz](https://kimvayne.xyz)에 모든 내용이 담겨 있다고!

---

## 🛠️ Key Skills

<table>
  <tr>
    <td><b>인프라 & 아키텍처</b></td>
    <td><b>개발 & API</b></td>
    <td><b>클라우드 & 도구</b></td>
  </tr>
  <tr>
    <td>
      ✅ Infrastructure 구축 및 관리<br>
      ✅ 마이크로 서비스 아키텍처 설계<br>
      ✅ Kubernetes 클러스터 운영<br>
      ✅ CI/CD 파이프라인 구축
    </td>
    <td>
      ✅ 데이터베이스 설계 및 최적화<br>
      ✅ API 설계 및 개발<br>
      ✅ L2 Mikrotik Router 세팅<br>
      ✅ Vagrant + Ansible 통한 자동화
    </td>
    <td>
      ✅ PLG 스택 모니터링 및 로깅<br>
      ✅ 오라클 클라우드 VM<br>
      ✅ Kali Linux(취미)<br>
      ✅ 각종 AI Tool 적극 활용
    </td>
  </tr>
</table>

---

## 💼 Experience

### 🌐 MOOLMEOW.COM - 1인 개발 Home Lab
#### 2025.03 - 현재

- **On-Premise 환경에서 Mac mini m2 pro 단일 기기로 Kubernetes 클러스터 설계 및 구축**
- **MikroTik 라우터 DHCP server 생성 및 홈랩 가정용 IP 분리, 국가별 방화벽 및 포트 포워딩 설정**
- **Vagrant + Ansible을 활용하여 멱등성 보장한 자동화**
- **Rook-Ceph → host-path → local storage → NFS 스토리지 설치 시 구성 변경**
- **Jenkins, ArgoCD, Docker Registry를 활용한 CI/CD 파이프라인 구현**
- **Prometheus, Loki, Grafana를 활용한 모니터링 시스템 구축**
- **Golang 기반 MSA 설계 및 백엔드 개발 feat.Gin, gRPC, PASETO**

### L2-L7 네트워크 아키텍처 설계 및 구현
<details>
<summary>📌 구체적인 프로젝트 내용 확인하기</summary>

#### 문제
클라우드 비용 절감을 위한 온프레미스 환경 필요 및 복잡한 네트워크 구성 요구

#### 해결
- MikroTik Router에서 DHCP 서버 생성 및 IP 서브넷 분리, Firewall, NAT, 인터페이스 브리지 직접 구성
- Calico CNI(L3), MetalLB(L4), NGINX Ingress Controller(L7) 기반의 종합 네트워킹 아키텍처 설계

#### 결과
- 클라우드 대비 월 30만원 이상 비용 절감 및 성능 안정화
- L2-L7까지 완전한 네트워크 스택 제어 및 관리 역량 확보
</details>

### Kubernetes 리소스 관리 전략
<details>
<summary>📌 구체적인 프로젝트 내용 확인하기</summary>

#### 문제
- 제한된 하드웨어(Mac Mini)에서 모든 필수 서비스 운영 필요
- 컨트롤 플레인 노드 리소스 부족으로 인한 서비스 중단 위험

#### 해결
- 테인트/톨러레이션 활용: 마스터 노드에 `node-role.kubernetes.io/control-plane` 테인트 적용
- Master Node - 6cpu 8/128 Jenkins, ArgoCD, MinIO 등 핵심 서비스 안정적 운영
- Worker Node - 2cpu 4/64 Promethus Loki Gragana + Back-End application 운영
- 워크로드 특성에 따른 노드 배치: 상태 유지 서비스는 마스터, 모니터링 및 로깅 서비스는 워커 노드에 배치
- 스택 리소스 제한(limits/requests) 정밀 설정: 모든 워크로드에 CPU/메모리 한계 구체적 설정

#### 결과
- 자원 사용률 30% 이상 개선 및 클러스터 전반적 안정성 확보
</details>

### 애플 실리콘 아키텍처 호환성 문제 해결
<details>
<summary>📌 구체적인 프로젝트 내용 확인하기</summary>

#### 문제
Mac Mini M2 Pro(ARM 아키텍처)에서의 다양한 호환성 문제 발생

#### 해결
- VMware Fusion+Terraform 호환성 문제로 VirtualBox+Vagrant+Ansible 조합으로 전환
- Harbor가 ARM 미지원 문제 해결을 위해 Docker Registry와 MinIO 조합으로 대체
- macOS 최신 보안 정책으로 인한 NFS 권한 문제 해결을 위한 세부 옵션 튜닝

#### 결과
- 플랫폼 제약에 구애받지 않는 인프라 구축 역량 강화
</details>

### 최적 스토리지 솔루션 선정 및 구현
<details>
<summary>📌 구체적인 프로젝트 내용 확인하기</summary>

#### 문제
컨테이너 재시작 시 데이터 유실 이슈 및 제한된 환경에서의 스토리지 선택

#### 해결
- 다양한 스토리지 솔루션 비교 검증: rook-ceph(리소스 부족), hostPath(fsync() issue), local-storage(호스트 공유 문제)
- Rook-Ceph은 유일하게 리소스 부족으로 인하여 MinIO와 같은 경량 스택으로 변경
- 최종적으로 NFS + StorageClass 구현으로 호스트와 VM 간 데이터 공유 구조 설계
- NFSv3 강제 설정 및 세부 마운트 옵션 튜닝으로 안정성 확보

#### 결과
- Jenkins, ArgoCD, MinIO 등 상태 유지 필요 서비스의 99.9% 가용성 달성
</details>

### 👨‍💻 TOPTOON 해외서비스개발부 - Back-end Dev.
#### 서울 | 2022.04 - 2023.12

- **Node.js / TypeScript / NestJS를 활용한 백엔드 API 설계 및 개발**
- **고객 서비스센터, 공지사항/FAQ 개발**
- **원인을 찾지 못하고 있던 문제를 사용자의 행동을 통하여 논리적 분석을 통해 원인 파악**
- **사용자 계정 삭제 반복 데이터 분석을 통해 무료 티켓 이벤트 로직 취약점 발견**
- **Docker 빌드 개선을 통하여 빌드 시간 수 분 단축**

---

## 🎓 Education

<table>
  <tr>
    <td><b>한동대학교</b></td>
    <td>시각디자인 & 영어 복수전공</td>
    <td>2005.03 - 2014.08</td>
  </tr>
  <tr>
    <td><b>코드스테이츠 소프트웨어 엔지니어링</b></td>
    <td>Node.js, React 교육 이수</td>
    <td>2021.05 - 2021.12</td>
  </tr>
</table>

---

## 📜 Certifications

<table>
  <tr>
    <td><b>쿠버네티스 전문가 양성 과정 수료</b></td>
    <td>Goorm</td>
    <td>2024.01 - 2024.04</td>
  </tr>
</table>

---

## 🌍 Additional Experience

<table>
  <tr>
    <td><b>영국 런던 Jubilee Lodge Centre 봉사활동</b></td>
    <td>Vitalise</td>
    <td>2006.02 - 2006.12</td>
  </tr>
</table>

---

<div align="center">
  <i>물뮤(moolmeow)는 차근차근 개발중</i>
</div>
