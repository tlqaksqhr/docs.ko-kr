---
title: "쿼리 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 093c22f5-3294-4642-857a-5252233d6796
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# 쿼리 지원
SQL 워크플로 인스턴스 저장소는 잘 알려진 속성 집합을 저장소에 기록합니다.사용자는 이러한 속성을 기반으로 인스턴스를 쿼리할 수 있습니다.다음은 잘 알려진 일부 속성 목록입니다.  
  
-   **Site Name.** 서비스를 포함하는 웹 사이트의 이름입니다.  
  
-   **Relative Application Path.** 웹 사이트에 상대적인 응용 프로그램 경로입니다.  
  
-   **Relative Service Path.** 응용 프로그램에 상대적인 서비스 경로입니다.  
  
-   **Service Name.** 서비스의 이름입니다.  
  
-   **Service Namespace.** 서비스에 사용되는 네임스페이스의 이름입니다.  
  
-   **Current Machine.**  
  
-   **Last Machine**.워크플로 서비스 인스턴스가 마지막으로 실행된 컴퓨터입니다.  
  
> [!NOTE]
>  워크플로 서비스 호스트를 사용하는 자체 호스팅 시나리오의 경우 마지막 네 속성만 채워집니다.워크플로 응용 프로그램 시나리오의 경우 마지막 속성만 채워집니다.  
  
 워크플로 런타임에서 처음 세 속성에 대한 값을 제공합니다.워크플로 서비스 호스트는 **Suspend Reason** 속성 값을 제공합니다.SQL 워크플로 인스턴스 저장소는 **Last Updated Machine** 속성 값을 제공합니다.  
  
 또한 SQL 워크플로 인스턴스 저장소 기능을 사용하면 사용자 지정 속성을 지정하여 지속성 데이터베이스에 값을 저장한 다음 쿼리에서 사용할 수 있습니다.사용자 지정 승격에 대한 자세한 내용은 [저장소 확장성](../../../docs/framework/windows-workflow-foundation//store-extensibility.md)을 참조하십시오.  
  
## 뷰  
 인스턴스 저장소에는 다음 뷰가 포함됩니다.자세한 내용은 [지속성 데이터베이스 스키마](../../../docs/framework/windows-workflow-foundation//persistence-database-schema.md)를 참조하십시오.  
  
### Instances 뷰  
 인스턴스 뷰에는 다음 필드가 포함됩니다.  
  
1.  **Id**  
  
2.  **PendingTimer**  
  
3.  **CreationTime**  
  
4.  **LastUpdatedTime**  
  
5.  **ServiceDeploymentId**  
  
6.  **SuspensionExceptionName**  
  
7.  **SuspensionReason**  
  
8.  **ActiveBookmarks**  
  
9. **CurrentMachine**  
  
10. **LastMachine**  
  
11. **ExecutionStatus**  
  
12. **IsInitialized**  
  
13. **IsSuspended**  
  
14. **IsCompleted**  
  
15. **EncodingOption**  
  
16. **ReadWritePrimitiveDataProperties**  
  
17. **WriteOnlyPrimitiveDataProperties**  
  
18. **ReadWriteComplexDataProperties**  
  
19. **WriteOnlyComplexDataProperties**  
  
### ServiceDeployments 뷰  
 ServiceDeployments 뷰에는 다음 필드가 포함됩니다.  
  
1.  **SiteName**  
  
2.  **RelativeServicePath**  
  
3.  **RelativeApplicationPath**  
  
4.  **ServiceName**  
  
5.  **ServiceNamespace**  
  
### InstancePromotedProperties 뷰  
 InstancePromotedProperties 뷰에는 다음 필드가 포함됩니다.승격된 속성에 대한 자세한 내용은 [저장소 확장성](../../../docs/framework/windows-workflow-foundation//store-extensibility.md) 항목을 참조하십시오.  
  
1.  **InstanceId**  
  
2.  **EncodingOption**  
  
3.  **PromotionName**  
  
4.  **Value\#**\(**Value1**에서 **Value64** 사이의 필드 범위\)