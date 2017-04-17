---
title: "인스턴스 활성화 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 134c3f70-5d4e-46d0-9d49-469a6643edd8
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 인스턴스 활성화
SQL 워크플로 인스턴스 저장소는 정기적으로 다시 시작되어 지속성 데이터베이스에서 실행 가능하거나 활성화 가능한 워크플로 인스턴스를 검색하는 내부 태스크를 실행합니다.실행 가능한 워크플로 인스턴스를 발견하면 해당 인스턴스를 활성화할 수 있는 워크플로 호스트에 알려 줍니다.인스턴스 저장소에서 활성화 가능한 워크플로 인스턴스를 발견하면 워크플로 호스트를 활성화하여 워크플로 인스턴스를 실행하는 일반 호스트에 알려 줍니다.이 항목의 다음 단원에서는 인스턴스 활성화 프로세스에 대해 자세히 설명합니다.  
  
##  <a name="RunnableSection"></a> 실행 가능한 워크플로 인스턴스 검색 및 활성화  
 SQL 워크플로 인스턴스 저장소에서는 워크플로 인스턴스가 일시 중단 상태 또는 완료 상태가 아니고 다음 조건을 충족할 경우 해당 인스턴스를 *실행 가능한* 것으로 간주합니다.  
  
-   인스턴스가 잠금 해제되었으며 만료된 보류 중인 타이머가 있습니다.  
  
-   인스턴스에 만료된 잠금이 있습니다.  
  
-   인스턴스가 잠금 해제되었으며 **실행 중** 상태입니다.  
  
 SQL 워크플로 인스턴스 저장소에서는 실행 가능한 인스턴스가 발견되면 <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent>를 발생시킵니다.그러면 SqlWorkflowInstanceStore는 저장소에서 <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>가 한 번 호출될 때까지 모니터링을 중지합니다.  
  
 <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent>에 대해 구독되고 인스턴스를 로드할 수 있는 워크플로 호스트는 인스턴스 저장소에 대해 <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>를 실행하여 인스턴스를 메모리로 로드합니다.호스트와 인스턴스의 **WorkflowServiceType** 메타데이터 속성이 동일한 값으로 설정되어 있으면 워크플로 호스트에서 워크플로 인스턴스를 로드할 수 있는 것으로 간주됩니다.  
  
## 활성화 가능한 워크플로 인스턴스 검색 및 활성화  
 인스턴스가 실행 가능하고 컴퓨터에서 실행되는 인스턴스를 로드할 수 있는 워크플로 호스트가 없는 경우 워크플로 인스턴스가 *활성화 가능한* 것으로 간주됩니다.실행 가능한 워크플로 인스턴스의 정의는 위의 "실행 가능한 워크플로 인스턴스 검색 및 활성화"를 참조하십시오.  
  
 SQL 워크플로 인스턴스 저장소에서는 데이터베이스에서 활성화 가능한 워크플로 인스턴스가 발견되면 <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent>를 발생시킵니다.그러면 SqlWorkflowInstanceStore는 저장소에서 <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>가 한 번 호출될 때까지 모니터링을 중지합니다.  
  
 <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent>에 대해 구독되는 일반 호스트는 이벤트를 수신할 경우 인스턴스 저장소에 대해 <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>를 실행하여 워크플로 호스트를 만드는 데 필요한 활성화 매개 변수를 가져옵니다.일반 호스트는 이러한 활성화 매개 변수를 사용하여 워크플로 호스트를 만들고, 워크플로 호스트가 실행 가능한 서비스 인스턴스를 로드 및 실행합니다.  
  
## 일반 호스트  
 일반 호스트는 일반 호스트에 대한 **WorkflowServiceType** 메타데이터 속성 값이 **WorkflowServiceType.Any**로 설정되어 모든 워크플로 유형을 처리할 수 있는 호스트입니다.일반 호스트에는 **ActivationType**이라는 XName 매개 변수가 있습니다.  
  
 현재 SQL 워크플로 인스턴스 저장소는 ActivationType 매개 변수 값이 **WAS**로 설정된 일반 호스트를 지원합니다.ActivationType이 WAS로 설정되어 있지 않으면 SQL 워크플로 인스턴스 저장소는 <xref:System.Runtime.DurableInstancing.InstancePersistenceException>을 throw합니다.[!INCLUDE[dublin](../../../includes/dublin-md.md)]과 함께 제공되는 워크플로 관리 서비스는 활성화 유형이 **WAS**로 설정된 일반 호스트입니다.  
  
 WAS 활성화를 위해 일반 호스트에는 새 호스트를 활성화할 수 있는 끝점 주소를 파생하는 활성화 매개 변수 집합이 필요합니다.WAS 활성화를 위한 활성화 매개 변수는 사이트 이름, 사이트에 상대적인 응용 프로그램 경로 및 응용 프로그램에 상대적인 서비스 경로입니다.SQL 워크플로 인스턴스 저장소는 <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>를 실행하는 동안 이러한 활성화 매개 변수를 저장합니다.  
  
## 실행 가능한 인스턴스 검색 기간  
 SQL 워크플로 인스턴스 저장소의 **Runnable Instances Detection Period** 속성은 SQL 워크플로 인스턴스 저장소에서 이전 검색 주기 이후에 검색 태스크를 실행하여 지속성 데이터베이스에서 실행 가능한 워크플로 인스턴스 또는 활성화 가능한 워크플로 인스턴스를 검색하는 기간을 지정합니다.이 속성에 대한 자세한 내용은 [실행 가능한 인스턴스 검색 기간](../../../docs/framework/windows-workflow-foundation//runnable-instances-detection-period.md)을 참조하십시오.