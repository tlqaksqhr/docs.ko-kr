---
title: "방법: 워크플로 및 워크플로 서비스에 지속성 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 방법: 워크플로 및 워크플로 서비스에 지속성 사용
이 항목에서는 워크플로 및 워크플로 서비스에 대해 지속성을 사용하도록 설정하는 방법에 대해 설명합니다.  
  
## 워크플로에 대해 지속성 사용  
 <xref:System.Activities.WorkflowApplication> 클래스의 <xref:System.Activities.WorkflowApplication.InstanceStore%2A> 속성을 사용하여 인스턴스 저장소를 **WorkflowApplication**에 연결할 수 있습니다.<xref:System.Activities.WorkflowApplication.Persist%2A> 메서드는 응용 프로그램에 연결된 인스턴스 저장소에 워크플로를 저장하거나 유지합니다.<xref:System.Activities.WorkflowApplication.Unload%2A> 메서드는 인스턴스 저장소에 워크플로를 유지한 다음 메모리에서 인스턴스를 언로드합니다.**Load** 메서드는 인스턴스 지속성 저장소에 저장된 워크플로 데이터를 사용하여 워크플로를 메모리로 로드합니다.  
  
 **Persist** 메서드는 다음 단계를 수행합니다.  
  
1.  워크플로 스케줄러를 일시 중지하고 워크플로가 유휴 상태로 전환될 때까지 기다립니다.  
  
2.  워크플로를 지속성 저장소에 유지하거나 저장합니다.  
  
3.  워크플로 스케줄러를 다시 시작합니다.  
  
 **Unload** 메서드는 다음 단계를 수행합니다.  
  
1.  워크플로 스케줄러를 일시 중지하고 워크플로가 유휴 상태로 전환될 때까지 기다립니다.  
  
2.  워크플로를 지속성 저장소에 유지하거나 저장합니다.  
  
3.  워크플로 인스턴스를 메모리에서 삭제합니다.  
  
 워크플로가 비지속성 영역에 있는 경우에는 워크플로가 비지속성 영역을 종료할 때까지 **Persist** 메서드와 **Unload** 메서드가 모두 차단됩니다.비지속성 영역이 완료되면 메서드에서 지속 또는 언로드 작업을 계속합니다.제한 시간이 경과할 때까지 비지속성 영역이 완료되지 않거나 지속성 프로세스가 너무 오래 걸릴 경우 TimeoutException이 throw됩니다.  
  
## 코드에서 워크플로 서비스에 대해 지속성 사용  
 <xref:System.ServiceModel.WorkflowServiceHost> 클래스의 **DurableInstancingOptions** 멤버는 인스턴스 저장소를 **WorkflowServiceHost**에 연결하는 데 사용할 수 있는 **InstanceStore** 속성이 있습니다.  
  
```  
  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
  
```  
  
 **WorkflowServiceHost**를 열 때 **DurableInstancingOptions.InstanceStore**가 null이 아니면 지속성이 자동으로 설정됩니다.  
  
 일반적으로 서비스 동작은 **InstanceStore** 속성을 사용하여 워크플로 서비스 호스트에 사용할 구체적인 인스턴스 저장소를 제공합니다.예를 들어 SqlWorkflowInstanceStoreBehavior는 **SqlWorkflowInstanceStore** 인스턴스를 만들고 구성한 다음 **DurableInstancingOptions.InstanceStore**에 할당합니다.  
  
## 응용 프로그램 구성 파일을 사용하여 워크플로 서비스에 지속성 허용  
 다음 코드를 app.config 또는 web.config 파일에 추가하여 응용 프로그램 구성 파일을 통해 지속성을 사용하도록 설정할 수 있습니다.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name=”myBehavior”>  
          <SqlWorkflowInstanceStore connectionString=”Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase”>  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
  
```