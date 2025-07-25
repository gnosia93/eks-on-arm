## eks-on-arm ## 
![](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/images/ws-archi-1.png)
이 워크샵에서는 x86 노드로 구성된 eks 클러스터를 aws graviton 인스턴스로 전환하는 방법을 설명합니다. 실습을 진행하기 위해서 terraform, kubectl, eksctl, helm 등을 로컬 PC 에 설치하고, terraform 으로 인프라를 프로비저닝 합니다. AWS 계정은 이미 생성되어 있다고 가정하므로 본 워크샵에서는 계정 생성 및 억세스 키 설정에 대해서 다루지 않습니다.  

## Scenario ##

1. [EKS 클러스터 생성하기(eks provision)](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/1.infra.md)

2. [멀티 아키텍처 이미지 만들기(multi architecture image build)](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/2.multi-arch-image.md)
       
   - [AWS Codepipeline Native Build](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/2.multi-arch-codepipe.md)
   - [Jenkins CI Pipline Native Build](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/2.multi-arch-jenkins.md)
   - [Gitlab Multi Architecture Build](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/2.multi-arch-gitlab.md)
   - https://www.docker.com/blog/speed-up-building-with-docker-buildx-and-graviton2-ec2/
         
3. [X86 노드에서 어플리케이션 실행하기](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/3.x86-app.md)
       
4. [Graviton 노드 추가하기](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/4.graviton-nodegroup.md)

5. [어플리케이션 마이그레이션 하기](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/5.app-mig.md)

    - [ALB 가중치 기반 라우팅 활용하기](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/5-1.alb-weight-routing.md)
    - [Istio 버추얼 서비스 활용하기](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/5-2.istio-routing.md)      

6. Karpenter - https://www.nops.io/blog/karpenter-vs-cluster-autoscaler-vs-nks/
  
7. 성능 측정하기
   
    - [프로메테우스 / 그라파나 설치](https://github.com/gnosia93/eks-grv-adp/blob/main/tutorial/6.perf-prometheus.md)
    - [대시보드 설정](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/6.perf-mon.md)
    - [부하 테스트(x86 vs 그라비톤)](https://github.com/gnosia93/eks-grv-mig/blob/main/tutorial/6.perf-ab.md)

8. Profiling

    - [perf를 이용한 자바 프로파일링](https://github.com/gnosia93/eks-on-arm/blob/main/tutorial/8.perf-profiling.md)
    - https://www.baeldung.com/java-flight-recorder-monitoring

9. Observability
    
   - endpoint(URL) latency - https://medium.com/@alex067/enabling-ingress-path-metrics-in-eks-aws-ingress-controller-47dc70b52828
     
## Blogs ##

* [Mixing AWS Graviton with x86 CPUs to optimize cost and resiliency using Amazon EKS](https://aws.amazon.com/blogs/compute/mixing-aws-graviton-with-x86-cpus-to-optimize-cost-and-resilience-using-amazon-eks/)
* [Considerations when transitioning workloads to AWS Graviton](https://github.com/aws/aws-graviton-getting-started/blob/main/transition-guide.md)
* [Optimizing Cloud Infrastructure: A DevOps Journey from x86 to ARM (Graviton) Architecture](https://medium.com/@Nick_Chekushkin/optimizing-cloud-infrastructure-a-devops-journey-from-x86-to-arm-graviton-architecture-78df829d39c6)
* https://bell-sw.com/announcements/2020/10/28/JVM-in-Linux-containers-surviving-the-isolation/
* [ARM의 ARMv9 아키텍처 발표: SVE2, 개선된 보안 및 향후 10년을 바라보며](https://blog.naver.com/steve5636/222295280395)
* [컨테이너 빌드 도구 선택을 위한 특성 및 성능 비교 (Kaniko, Buildah, Buildkit)](https://nangman14.tistory.com/92)
* [AWS Graviton Processors: An In-Depth Look at AWS’s ARM-Based Evolution](https://medium.com/@sufleio/aws-graviton-processors-an-in-depth-look-at-awss-arm-based-evolution-02ffc316ef1d)
  
## Revision History ##
* 2024-12-13 First Released

## Reference ##

* https://www.eksworkshop.com/
* https://github.com/aws-ia/terraform-aws-eks-blueprints
* https://workshops.aws/categories/Containers?tag=Graviton
* [How to rapidly scale your application with ALB on EKS (without losing traffic)](https://github.com/aws-samples/app-health-with-aws-load-balancer-controller/tree/main)
* [Simple Web Application of multi-arch images of Graviton3(c7g) and Intel/AMD(c6) instacnes](https://github.com/aws-samples/app-health-with-aws-load-balancer-controller/tree/main/simple-multiarch-app)
