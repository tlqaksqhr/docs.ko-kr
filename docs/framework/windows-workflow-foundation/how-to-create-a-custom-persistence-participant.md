---
title: '방법: 사용자 지정 지속성 참석자 만들기'
ms.date: 03/30/2017
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
ms.openlocfilehash: fcd96e41d8fc7b36f9dff5f10e9bc2d9034d79b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517243"
---
# <a name="how-to-create-a-custom-persistence-participant"></a>방법: 사용자 지정 지속성 참석자 만들기
다음 절차에서는 지속성 참석자를 만드는 단계에 대해 설명합니다. 참조는 [지 속성에 참여](http://go.microsoft.com/fwlink/?LinkID=177735) 샘플 및 [저장소 확장성](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) 지 속성 참가자의 샘플 구현에 대 한 항목입니다.  
  
1.  <xref:System.Activities.Persistence.PersistenceParticipant> 또는 <xref:System.Activities.Persistence.PersistenceIOParticipant> 클래스에서 파생되는 클래스를 만듭니다. PersistenceIOParticipant 클래스는 I/O 작업에 사용할 수 있을 뿐만 아니라 PersistenceParticipant 클래스와 동일한 확장 지점을 제공 합니다. 다음 단계 중 하나 이상을 수행합니다.  
  
2.  <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> 메서드를 구현합니다. **CollectValues** 메서드는 두 가지 사전 매개 변수, 읽기/쓰기 값 저장을 위한 사전 매개 변수와 (나중에 쿼리에서 사용 되는) 쓰기 전용 값을 저장 합니다. 이 메서드에서 이 두 사전 매개 변수를 지속성 참석자 관련 데이터로 채워야 합니다. 각 사전은 값 이름을 키로 포함하고 값을 <xref:System.Runtime.DurableInstancing.InstanceValue> 개체로 포함합니다.  
  
     ReadWriteValues 사전의 값 패키지 되어 **InstanceValue** 개체입니다. 쓰기 전용 사전의 값 패키지 되어 **InstanceValue** 은 InstanceValueOptions.Optional 및 InstanceValueOption.WriteOnly가 설정 된 개체입니다. 각 **InstanceValue** 에서 제공 되는 **CollectValues** 구현은 모든 지 속성 참석자에 대해 고유한 이름이 있어야 합니다.  
  
    ```  
    protected virtual void CollectValues (out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
3.  <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> 메서드를 구현합니다. **MapValues** 메서드 매개 변수에서와 유사한 두 개의 매개 변수를 사용 하는 **CollectValues** 메서드에 전달 합니다. 수집 된 모든 값의 **CollectValues** 단계는이 사전 매개 변수를 통해 전달 됩니다. 추가 된 새 값의 **MapValues** 단계 쓰기 전용 값에 추가 됩니다.  쓰기 전용 사전은 인스턴스 값에 직접 연결하지 않고 데이터를 외부 소스에 제공하는 데 사용됩니다. 각 값의 구현을 통해 제공 되는 **MapValues** 메서드 모든 지 속성 참석자에 대해 고유한 이름이 있어야 합니다.  
  
    ```  
    protected virtual IDictionary<XName,Object> MapValues (IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
     <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> 메서드는 <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>가 제공하지 않지만, <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>에서 아직 처리하지 않은 다른 지속성 참석자가 제공한 다른 값에 대한 종속성을 허용하는 기능을 제공합니다.  
  
4.  구현 된 **PublishValues** 메서드. **PublishValues** 메서드는 지 속성 저장소에서 로드 된 모든 값이 들어 있는 사전을 수신 합니다.  
  
    ```  
    protected virtual void PublishValues (IDictionary<XName,Object> readWriteValues)  
    ```  
  
5.  구현 된 **BeginOnSave** 메서드 참가자가 I/O 지 속성 참가자 경우. 이 메서드는 저장 작업 중에 호출됩니다. 이 방법에서는 유지 (저장) 워크플로 인스턴스를 보충 모델 I/O를 수행 해야 합니다.  호스트에서 해당 지속성 명령에 대해 트랜잭션을 사용할 경우 동일한 트랜잭션이 Transaction.Current에 제공됩니다.  또한 PersistenceIOParticipants에서는 트랜잭션 일관성 요구 사항을 알릴 수 있습니다. 이 경우 호스트에서는 요구 사항과 달리 사용되지 않는 지속성 에피소드에 대한 트랜잭션을 만듭니다.  
  
    ```  
    protected virtual IAsyncResult BeginOnSave (IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```  
  
6.  구현 된 **BeginOnLoad** 메서드 참가자가 I/O 지 속성 참가자 경우. 이 메서드는 로드 작업 중에 호출됩니다. 이 방법에서는 I/O 로드에 따른의 워크플로 인스턴스를 수행 해야 합니다. 호스트에서 해당 지속성 명령에 대해 트랜잭션을 사용할 경우 동일한 트랜잭션이 Transaction.Current에 제공됩니다. 또한 I/O 지 속성 참가자에서 경우 호스트 만들어 지 속성 에피소드에 대 한 트랜잭션을 달리 사용 되지 않는 하나 경우 트랜잭션 일관성 요구 사항을 알릴 수 있습니다.  
  
    ```  
    protected virtual IAsyncResult BeginOnLoad (IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```
