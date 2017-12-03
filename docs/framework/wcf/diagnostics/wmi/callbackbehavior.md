---
title: CallbackBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c10d9e26f86fa569b1a607c9b755f32ee97792a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="callbackbehavior"></a><span data-ttu-id="e8fb6-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="e8fb6-102">CallbackBehavior</span></span>
<span data-ttu-id="e8fb6-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="e8fb6-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8fb6-104">구문</span><span class="sxs-lookup"><span data-stu-id="e8fb6-104">Syntax</span></span>  
  
```  
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e8fb6-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e8fb6-105">Methods</span></span>  
 <span data-ttu-id="e8fb6-106">CallbackBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fb6-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e8fb6-107">속성</span><span class="sxs-lookup"><span data-stu-id="e8fb6-107">Properties</span></span>  
 <span data-ttu-id="e8fb6-108">CallbackBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fb6-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="e8fb6-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="e8fb6-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="e8fb6-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="e8fb6-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="e8fb6-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e8fb6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8fb6-112">true이면 서비스가 이중 세션을 닫을 경우 세션이 자동으로 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="e8fb6-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="e8fb6-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="e8fb6-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="e8fb6-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="e8fb6-114">Data type: string</span></span>  
<span data-ttu-id="e8fb6-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e8fb6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8fb6-116">서비스가 하나의 스레드, 여러 개의 스레드 또는 재진입 호출을 지원할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fb6-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="e8fb6-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="e8fb6-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="e8fb6-118">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="e8fb6-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="e8fb6-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e8fb6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8fb6-120">연결되어 있는 알 수 없는 serialization 데이터를 보낼지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e8fb6-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="e8fb6-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="e8fb6-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="e8fb6-122">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="e8fb6-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="e8fb6-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e8fb6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8fb6-124">선택하면 콜백 시 예외에 대한 세부 정보가 서비스로 반환되는 오류에 첨부됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8fb6-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="e8fb6-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="e8fb6-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="e8fb6-126">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="e8fb6-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="e8fb6-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e8fb6-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8fb6-128">serialize된 개체에 허용되는 최대 항목 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e8fb6-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="e8fb6-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="e8fb6-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="e8fb6-130">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="e8fb6-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="e8fb6-131">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e8fb6-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8fb6-132">현재 동기화 컨텍스트를 사용하여 스레드 실행을 선택할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fb6-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="e8fb6-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="e8fb6-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="e8fb6-134">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="e8fb6-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="e8fb6-135">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="e8fb6-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e8fb6-136">시스템 또는 응용 프로그램에서 SOAP MustUnderstand 헤더 처리를 적용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fb6-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8fb6-137">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8fb6-137">Requirements</span></span>  
  
|<span data-ttu-id="e8fb6-138">MOF</span><span class="sxs-lookup"><span data-stu-id="e8fb6-138">MOF</span></span>|<span data-ttu-id="e8fb6-139">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fb6-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e8fb6-140">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="e8fb6-140">Namespace</span></span>|<span data-ttu-id="e8fb6-141">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8fb6-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8fb6-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8fb6-142">See Also</span></span>  
 <xref:System.ServiceModel.CallbackBehaviorAttribute>
