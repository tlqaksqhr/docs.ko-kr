---
title: "방법: 사용자 지정 지속성 참석자 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 방법: 사용자 지정 지속성 참석자 만들기
다음 절차에서는 지속성 참석자를 만드는 단계에 대해 설명합니다.지속성 참석자에 대한 샘플 구현은 [지속성 참석](http://go.microsoft.com/fwlink/?LinkID=177735) 샘플 및 [저장소 확장성](../../../docs/framework/windows-workflow-foundation//store-extensibility.md) 항목을 참조하십시오.  
  
1.  <xref:System.Activities.Persistence.PersistenceParticipant> 또는 <xref:System.Activities.Persistence.PersistenceIOParticipant> 클래스에서 파생되는 클래스를 만듭니다.PersistenceIOParticipant 클래스는 PersistenceParticipant 클래스와 동일한 확장 지점을 제공할 뿐만 아니라 IO 작업에 참여할 수 있습니다.다음 단계 중 하나 이상을 수행합니다.  
  
2.  <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> 메서드를 구현합니다.**CollectValues** 메서드에는 두 가지 사전 매개 변수 즉, 읽기\/쓰기 값 저장을 위한 사전 매개 변수와 나중에 쿼리에서 사용되는 쓰기 전용 값 저장을 위한 사전 매개 변수가 있습니다.이 메서드에서 이 두 사전 매개 변수를 지속성 참석자 관련 데이터로 채워야 합니다.각 사전은 값 이름을 키로 포함하고 값을 <xref:System.Runtime.DurableInstancing.InstanceValue> 개체로 포함합니다.  
  
     readWriteValues 사전의 값은 **InstanceValue** 개체로 패키지됩니다.쓰기 전용 사전의 값은 InstanceValueOptions.Optional 및 InstanceValueOption.WriteOnly가 설정된 상태로 **InstanceValue** 개체로 패키지됩니다.모든 지속성 참석자를 통해 **CollectValues** 구현에서 제공되는 각 **InstanceValue**는 고유한 이름이 있어야 합니다.  
  
    ```  
    protected virtual void CollectValues (out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)  
  
    ```  
  
3.  <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> 메서드를 구현합니다.**MapValues** 메서드는 **CollectValues** 메서드에서 수신하는 매개 변수와 비슷한 두 매개 변수를 사용합니다.**CollectValues** 단계에서 수집되는 모든 값은 이 사전 매개 변수를 통해 전달됩니다.**MapValues** 단계에서 추가되는 새 값은 쓰기 전용 값에 추가됩니다.쓰기 전용 사전은 인스턴스 값에 직접 연결하지 않고 데이터를 외부 소스에 제공하는 데 사용됩니다.모든 지속성 참석자를 통해 **MapValues** 메서드 구현에서 제공되는 각 값은 고유한 이름이 있어야 합니다.  
  
    ```  
    protected virtual IDictionary<XName,Object> MapValues (IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
     <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> 메서드는  <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>가  제공하지 않지만, <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>에서 아직 처리하지 않은 다른 지속성 참석자가 제공한 다른 값에 대한 종속성을 허용하는 기능을 제공합니다.  
  
4.  **PublishValues** 메서드를 구현합니다.**PublishValues** 메서드는 지속성 저장소에서 로드되는 모든 값이 들어 있는 사전을 수신합니다.  
  
    ```  
    protected virtual void PublishValues (IDictionary<XName,Object> readWriteValues)  
  
    ```  
  
5.  참석자가 지속성 IO 참석자인 경우 **BeginOnSave** 메서드를 구현합니다.이 메서드는 저장 작업 중에 호출됩니다.이 메서드에서는 워크플로 인스턴스 유지\(저장\)에 따른 IO를 수행해야 합니다.호스트에서 해당 지속성 명령에 대해 트랜잭션을 사용할 경우 동일한 트랜잭션이 Transaction.Current에 제공됩니다.또한 PersistenceIOParticipants에서는 트랜잭션 일관성 요구 사항을 알릴 수 있습니다. 이 경우 호스트에서는 요구 사항과 달리 사용되지 않는 지속성 에피소드에 대한 트랜잭션을 만듭니다.  
  
    ```  
  
    protected virtual IAsyncResult BeginOnSave (IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```  
  
6.  참석자가 지속성 IO 참석자인 경우 **BeginOnLoad** 메서드를 구현합니다.이 메서드는 로드 작업 중에 호출됩니다.이 메서드에서는 워크플로 인스턴스 로드에 따른 IO를 수행해야 합니다.호스트에서 해당 지속성 명령에 대해 트랜잭션을 사용할 경우 동일한 트랜잭션이 Transaction.Current에 제공됩니다.또한 지속성 IO 참석자는 트랜잭션 일관성 요구 사항을 알릴 수 있습니다. 이 경우 호스트에서는 요구 사항과 달리 사용되지 않는 지속성 에피소드에 대한 트랜잭션을 만듭니다.  
  
    ```  
  
    protected virtual IAsyncResult BeginOnLoad (IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)  
  
    ```