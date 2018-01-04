---
title: "방법: 사용자 지정 지속성 참석자 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ebc83f100b4303b73ba2e6d3dc41d0f82e8f2c22
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-persistence-participant"></a><span data-ttu-id="d48ef-102">방법: 사용자 지정 지속성 참석자 만들기</span><span class="sxs-lookup"><span data-stu-id="d48ef-102">How to: Create a Custom Persistence Participant</span></span>
<span data-ttu-id="d48ef-103">다음 절차에서는 지속성 참석자를 만드는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-103">The following procedure has steps to create a persistence participant.</span></span> <span data-ttu-id="d48ef-104">참조는 [지 속성에 참여](http://go.microsoft.com/fwlink/?LinkID=177735) 샘플 및 [저장소 확장성](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) 지 속성 참가자의 샘플 구현에 대 한 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-104">See the [Participating in Persistence](http://go.microsoft.com/fwlink/?LinkID=177735) sample and [Store Extensibility](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) topic for sample implementations of persistence participants.</span></span>  
  
1.  <span data-ttu-id="d48ef-105"><xref:System.Activities.Persistence.PersistenceParticipant> 또는 <xref:System.Activities.Persistence.PersistenceIOParticipant> 클래스에서 파생되는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-105">Create a class deriving from the <xref:System.Activities.Persistence.PersistenceParticipant> or the <xref:System.Activities.Persistence.PersistenceIOParticipant> class.</span></span> <span data-ttu-id="d48ef-106">PersistenceIOParticipant 클래스는 PersistenceParticipant 클래스와 동일한 확장 지점을 제공할 뿐만 아니라 IO 작업에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-106">The PersistenceIOParticipant class offers the same extensibility points as the PersistenceParticipant class in addition to being able to participate in IO operations.</span></span> <span data-ttu-id="d48ef-107">다음 단계 중 하나 이상을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-107">Follow one or more of the following steps.</span></span>  
  
2.  <span data-ttu-id="d48ef-108"><xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-108">Implement the <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> method.</span></span> <span data-ttu-id="d48ef-109">**CollectValues** 메서드는 두 가지 사전 매개 변수, 읽기/쓰기 값 저장을 위한 사전 매개 변수와 (나중에 쿼리에서 사용 되는) 쓰기 전용 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-109">The **CollectValues** method has two dictionary parameters, one for storing read/write values and the other one for storing write-only values (used later in queries).</span></span> <span data-ttu-id="d48ef-110">이 메서드에서 이 두 사전 매개 변수를 지속성 참석자 관련 데이터로 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-110">In this method, you should populate these dictionaries with data that is specific to a persistence participant.</span></span> <span data-ttu-id="d48ef-111">각 사전은 값 이름을 키로 포함하고 값을 <xref:System.Runtime.DurableInstancing.InstanceValue> 개체로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-111">Each dictionary contains the name of the value as the key and the value itself as an <xref:System.Runtime.DurableInstancing.InstanceValue> object.</span></span>  
  
     <span data-ttu-id="d48ef-112">ReadWriteValues 사전의 값 패키지 되어 **InstanceValue** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-112">The values in the readWriteValues dictionary are packaged as **InstanceValue** objects.</span></span> <span data-ttu-id="d48ef-113">쓰기 전용 사전의 값 패키지 되어 **InstanceValue** 은 InstanceValueOptions.Optional 및 InstanceValueOption.WriteOnly가 설정 된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-113">The values in the write-only dictionary are packaged as **InstanceValue** objects with InstanceValueOptions.Optional and InstanceValueOption.WriteOnly set.</span></span> <span data-ttu-id="d48ef-114">각 **InstanceValue** 에서 제공 되는 **CollectValues** 구현은 모든 지 속성 참석자에 대해 고유한 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-114">Each **InstanceValue** provided by the **CollectValues** implementations across all persistence participants must have a unique name.</span></span>  
  
    ```  
    protected virtual void CollectValues (out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
3.  <span data-ttu-id="d48ef-115"><xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-115">Implement the <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> method.</span></span> <span data-ttu-id="d48ef-116">**MapValues** 메서드 매개 변수에서와 유사한 두 개의 매개 변수를 사용 하는 **CollectValues** 메서드에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-116">The **MapValues** method takes two parameters that are similar to the parameters that the **CollectValues** method receives.</span></span> <span data-ttu-id="d48ef-117">수집 된 모든 값의 **CollectValues** 단계는이 사전 매개 변수를 통해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-117">All the values collected in the **CollectValues** stage are passed through these dictionary parameters.</span></span> <span data-ttu-id="d48ef-118">추가 된 새 값의 **MapValues** 단계 쓰기 전용 값에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-118">The new values added by the **MapValues** stage are added to the write-only values.</span></span>  <span data-ttu-id="d48ef-119">쓰기 전용 사전은 인스턴스 값에 직접 연결하지 않고 데이터를 외부 소스에 제공하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-119">The write-only dictionary is used to provide data to an external source not directly associated with the instance values.</span></span> <span data-ttu-id="d48ef-120">각 값의 구현을 통해 제공 되는 **MapValues** 메서드 모든 지 속성 참석자에 대해 고유한 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-120">Each value provided by implementations of the **MapValues** method across all persistence participants must have a unique name.</span></span>  
  
    ```  
    protected virtual IDictionary<XName,Object> MapValues (IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
     <span data-ttu-id="d48ef-121"><xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> 메서드는 <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>가 제공하지 않지만, <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>에서 아직 처리하지 않은 다른 지속성 참석자가 제공한 다른 값에 대한 종속성을 허용하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-121">The <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> method provides functionality that <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> does not, in that it allows for a dependency on another value provided by another persistence participant that hasn’t been processed by <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> yet.</span></span>  
  
4.  <span data-ttu-id="d48ef-122">구현 된 **PublishValues** 메서드.</span><span class="sxs-lookup"><span data-stu-id="d48ef-122">Implement the **PublishValues** method.</span></span> <span data-ttu-id="d48ef-123">**PublishValues** 메서드는 지 속성 저장소에서 로드 된 모든 값이 들어 있는 사전을 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-123">The **PublishValues** method receives a dictionary containing all the values loaded from the persistence store.</span></span>  
  
    ```  
    protected virtual void PublishValues (IDictionary<XName,Object> readWriteValues)  
    ```  
  
5.  <span data-ttu-id="d48ef-124">구현 된 **BeginOnSave** 참석자가 지 속성 IO 참가자 메서드.</span><span class="sxs-lookup"><span data-stu-id="d48ef-124">Implement the **BeginOnSave** method if the participant is a persistence IO participant.</span></span> <span data-ttu-id="d48ef-125">이 메서드는 저장 작업 중에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-125">This method is called during a Save operation.</span></span> <span data-ttu-id="d48ef-126">이 메서드에서는 워크플로 인스턴스 유지(저장)에 따른 IO를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-126">In this method, you should perform IO adjunct to the persisting (saving) workflow instances.</span></span>  <span data-ttu-id="d48ef-127">호스트에서 해당 지속성 명령에 대해 트랜잭션을 사용할 경우 동일한 트랜잭션이 Transaction.Current에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-127">If the host is using a transaction for the corresponding persistence command, the same transaction is provided in Transaction.Current.</span></span>  <span data-ttu-id="d48ef-128">또한 PersistenceIOParticipants에서는 트랜잭션 일관성 요구 사항을 알릴 수 있습니다. 이 경우 호스트에서는 요구 사항과 달리 사용되지 않는 지속성 에피소드에 대한 트랜잭션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-128">Additionally, PersistenceIOParticipants may advertise a transactional consistency requirement, in which case the host creates a transaction for the persistence episode if one would not otherwise be used.</span></span>  
  
    ```  
    protected virtual IAsyncResult BeginOnSave (IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```  
  
6.  <span data-ttu-id="d48ef-129">구현 된 **BeginOnLoad** 참석자가 지 속성 IO 참가자 메서드.</span><span class="sxs-lookup"><span data-stu-id="d48ef-129">Implement the **BeginOnLoad** method if the participant is a persistence IO participant.</span></span> <span data-ttu-id="d48ef-130">이 메서드는 로드 작업 중에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-130">This method is called during a Load operation.</span></span> <span data-ttu-id="d48ef-131">이 메서드에서는 워크플로 인스턴스 로드에 따른 IO를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-131">In this method, you should perform IO adjunct to the loading of workflow instances.</span></span> <span data-ttu-id="d48ef-132">호스트에서 해당 지속성 명령에 대해 트랜잭션을 사용할 경우 동일한 트랜잭션이 Transaction.Current에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-132">If the host is using a transaction for the corresponding persistence command, the same transaction is provided in Transaction.Current.</span></span> <span data-ttu-id="d48ef-133">또한 지속성 IO 참석자는 트랜잭션 일관성 요구 사항을 알릴 수 있습니다. 이 경우 호스트에서는 요구 사항과 달리 사용되지 않는 지속성 에피소드에 대한 트랜잭션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d48ef-133">Additionally, Persistence IO participants may advertise a transactional consistency requirement, in which case the host creates a transaction for the persistence episode if one would not otherwise be used.</span></span>  
  
    ```  
    protected virtual IAsyncResult BeginOnLoad (IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```
