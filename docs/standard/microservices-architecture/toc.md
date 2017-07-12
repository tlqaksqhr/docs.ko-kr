

# [.NET 마이크로 서비스: 컨테이너화된 .NET 응용 프로그램을 위한 아키텍처](index.md)


## [컨테이너 및 Docker 소개](container-docker-introduction/index.md)


### [Docker란?](container-docker-introduction/docker-defined.md)


### [Docker 용어](container-docker-introduction/docker-terminology.md)


### [Docker 컨테이너, 이미지 및 레지스트리](container-docker-introduction/docker-containers-images-registries.md)


## [Docker 컨테이너에 대해 .NET Core와 .NET Framework 중에 선택](net-core-net-framework-containers/index.md)


### [일반 지침](net-core-net-framework-containers/general-guidance.md)


### [Docker 컨테이너에 대해 .NET Core를 선택할 경우](net-core-net-framework-containers/net-core-container-scenarios.md)


### [Docker 컨테이너에 대해 .NET Framework를 선택할 경우](net-core-net-framework-containers/net-framework-container-scenarios.md)


### [의사 결정 테이블: Docker에 사용할 .NET Framework](net-core-net-framework-containers/container-framework-choice-factors.md)


### [.NET 컨테이너에서 대상으로 지정할 OS](net-core-net-framework-containers/net-container-os-targets.md)


### [공식 .NET Docker 이미지](net-core-net-framework-containers/official-net-docker-images.md)


## [컨테이너 및 마이크로 서비스 기반 응용 프로그램 디자인](architect-microservice-container-applications/index.md)


### [모놀리식 응용 프로그램 컨테이너화](architect-microservice-container-applications/containerize-monolithic-applications.md)


### [Docker 응용 프로그램의 상태 및 데이터](architect-microservice-container-applications/docker-application-state-data.md)


### [서비스 지향 아키텍처](architect-microservice-container-applications/service-oriented-architecture.md)


### [마이크로 서비스 아키텍처](architect-microservice-container-applications/microservices-architecture.md)


### [마이크로 서비스별 데이터 주권](architect-microservice-container-applications/data-sovereignty-per-microservice.md)


### [논리적 아키텍처 및 물리적 아키텍처](architect-microservice-container-applications/logical-versus-physical-architecture.md)


### [분산 데이터 관리의 문제 및 솔루션](architect-microservice-container-applications/distributed-data-management.md)


### [각 마이크로 서비스의 도메인 모델 경계 식별](architect-microservice-container-applications/identify-microservice-domain-model-boundaries.md)


### [마이크로 서비스 간 통신](architect-microservice-container-applications/communication-between-microservices.md)


### [비동기 메시지 기반 통신](architect-microservice-container-applications/asynchronous-message-based-communication.md)


### [마이크로 서비스 API 및 계약 만들기, 개선 및 버전 관리](architect-microservice-container-applications/maintain-microservice-apis.md)


### [마이크로 서비스 주소 지정 기능 및 서비스 레지스트리](architect-microservice-container-applications/microservices-addressability-service-registry.md)


### [여러 마이크로 서비스에서 생성된 시각적 UI 셰이프 및 레이아웃을 포함하여 마이크로 서비스를 기반으로 복합 UI 만들기](architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md)


### [마이크로 서비스의 복원력 및 고가용성](architect-microservice-container-applications/resilient-high-availability-microservices.md)


### [높은 확장성 및 가용성을 위해 마이크로 서비스 및 다중 컨테이너 응용 프로그램 오케스트레이션](architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)


### [Azure Service Fabric 사용](architect-microservice-container-applications/using-azure-service-fabric.md)


## [Docker 기반 응용 프로그램에 대한 개발 프로세스](docker-application-development-process/index.md)


### [Docker 앱에 대한 개발 워크플로](docker-application-development-process/docker-app-development-workflow.md)


## [Linux 또는 Windows Nano 서버 호스트에 단일 컨테이너 기반 .NET Core 웹 응용 프로그램 배포](net-core-single-containers-linux-windows-server-hosts/index.md)


## [Windows 컨테이너로 레거시 모놀리식 .NET Framework 응용 프로그램 마이그레이션](containerize-net-framework-applications/index.md)


## [다중 컨테이너 및 마이크로 서비스 기반 NET 응용 프로그램 디자인 및 개발](multi-container-microservice-net-applications/index.md)


### [마이크로 서비스 지향 응용 프로그램 디자인](multi-container-microservice-net-applications/microservice-application-design.md)


### [단순 데이터 기반 CRUD 마이크로 서비스 만들기](multi-container-microservice-net-applications/data-driven-crud-microservice.md)


### [docker-compose.yml을 사용하여 다중 컨테이너 응용 프로그램 정의](multi-container-microservice-net-applications/multi-container-applications-docker-compose.md)


### [컨테이너로 실행되는 데이터베이스 서버 사용](multi-container-microservice-net-applications/database-server-container.md)


### [마이크로 서비스(통합 이벤트) 간 이벤트 기반 통신 구현](multi-container-microservice-net-applications/integration-event-based-microservice-communications.md)


### [RabbitMQ를 사용하여 개발 또는 테스트 환경에 대한 이벤트 서비스 구현](multi-container-microservice-net-applications/rabbitmq-event-bus-development-test-environment.md)


### [이벤트 구독](multi-container-microservice-net-applications/subscribe-events.md)


### [ASP.NET Core 서비스 및 웹앱 테스트](multi-container-microservice-net-applications/test-aspnet-core-services-web-apps.md)


## [DDD 및 CQRS 패턴을 사용하여 마이크로 서비스에서 비즈니스 복잡성 처리](microservice-ddd-cqrs-patterns/index.md)


### [마이크로 서비스에서 간소화된 CQRS 및 DDD 패턴 적용](microservice-ddd-cqrs-patterns/apply-simplified-microservice-cqrs-ddd-patterns.md)


### [eShopOnContainers의 DDD 마이크로 서비스에서 CQRS 및 CQS 방법 적용](microservice-ddd-cqrs-patterns/eshoponcontainers-cqrs-ddd-microservice.md)


### [CQRS 마이크로 서비스에서 읽기/쿼리 구현](microservice-ddd-cqrs-patterns/cqrs-microservice-reads.md)


### [DDD 지향 마이크로 서비스 디자인](microservice-ddd-cqrs-patterns/ddd-oriented-microservice.md)


### [마이크로 서비스 도메인 모델 디자인](microservice-ddd-cqrs-patterns/microservice-domain-model.md)


### [.NET Core를 사용하여 마이크로 서비스 도메인 모델 구현](microservice-ddd-cqrs-patterns/net-core-microservice-domain-model.md)


### [Seedwork(도메인 모델에 대해 재사용이 가능한 기본 클래스 및 인터페이스)](microservice-ddd-cqrs-patterns/seedwork-domain-model-base-classes-interfaces.md)


### [값 개체 구현](microservice-ddd-cqrs-patterns/implement-value-objects.md)


### [열거형 형식 대신 열거형 클래스 사용](microservice-ddd-cqrs-patterns/enumeration-classes-over-enum-types.md)


### [도메인 모델 레이어에서 유효성 검사 디자인](microservice-ddd-cqrs-patterns/domain-model-layer-validations.md)


### [클라이언트 쪽 유효성 검사(프레젠테이션 레이어의 유효성 검사)](microservice-ddd-cqrs-patterns/client-side-validation.md)


### [도메인 이벤트: 디자인 및 구현](microservice-ddd-cqrs-patterns/domain-events-design-implementation.md)


### [인프라 지속성 레이어 디자인](microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-design.md)


### [Entity Framework Core를 사용하여 인프라 지속성 레이어 구현](microservice-ddd-cqrs-patterns/infrastructure-persistence-layer-implemenation-entity-framework-core.md)


### [NoSQL 데이터베이스를 지속성 인프라로 사용](microservice-ddd-cqrs-patterns/nosql-database-persistence-infrastructure.md)


### [마이크로 서비스 응용 프로그램 레이어 및 웹 API 디자인](microservice-ddd-cqrs-patterns/microservice-application-layer-web-api-design.md)


### [웹 API를 사용하여 마이크로 서비스 응용 프로그램 레이어 구현](microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)


## [복원력 있는 응용 프로그램 구현](implement-resilient-applications/index.md)


### [부분 실패 처리](implement-resilient-applications/handle-partial-failure.md)


### [부분 실패 처리 전략](implement-resilient-applications/partial-failure-strategies.md)


### [지수 백오프를 사용하여 다시 시도 구현](implement-resilient-applications/implement-retries-exponential-backoff.md)


### [복원력 있는 Entity Framework Core SQL 연결 구현](implement-resilient-applications/implement-resilient-entity-framework-core-sql-connections.md)


### [지수 백오프를 사용하여 사용자 지정 HTTP 호출 다시 시도 구현](implement-resilient-applications/implement-custom-http-call-retries-exponential-backoff.md)


### [Polly와 함께 지수 백오프를 사용하여 HTTP 호출 다시 시도 구현](implement-resilient-applications/implement-http-call-retries-exponential-backoff-polly.md)


### [회로 차단기 패턴 구현](implement-resilient-applications/implement-circuit-breaker-pattern.md)


### [상태 모니터링](implement-resilient-applications/monitor-app-health.md)


## [NET 마이크로 서비스 및 웹 응용 프로그램 보안](secure-net-microservices-web-applications/index.md)


### [.NET 마이크로 서비스 및 웹 응용 프로그램의 권한 부여 정보](secure-net-microservices-web-applications/authorization-net-microservices-web-applications.md)


### [개발하는 동안 응용 프로그램 비밀 저장](secure-net-microservices-web-applications/developer-app-secrets-storage.md)


### [Azure Key Vault를 사용하여 프로덕션 시 비밀 보호](secure-net-microservices-web-applications/azure-key-vault-protects-secrets.md)


## [핵심 내용](key-takeaways.md)
