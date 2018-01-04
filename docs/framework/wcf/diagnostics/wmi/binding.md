---
title: Binding2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6553d1e1c030a30eed74ff81d3e07e28a9f25b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="binding"></a><span data-ttu-id="ae26e-102">바인딩</span><span class="sxs-lookup"><span data-stu-id="ae26e-102">Binding</span></span>
<span data-ttu-id="ae26e-103">wmi 바인딩</span><span class="sxs-lookup"><span data-stu-id="ae26e-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae26e-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae26e-104">Syntax</span></span>  
  
```  
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ae26e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ae26e-105">Methods</span></span>  
 <span data-ttu-id="ae26e-106">바인딩 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae26e-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ae26e-107">속성</span><span class="sxs-lookup"><span data-stu-id="ae26e-107">Properties</span></span>  
 <span data-ttu-id="ae26e-108">Binding 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae26e-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="ae26e-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="ae26e-109">BindingElements</span></span>  
 <span data-ttu-id="ae26e-110">데이터 형식: BindingElement array</span><span class="sxs-lookup"><span data-stu-id="ae26e-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="ae26e-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae26e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae26e-112">바인딩이 구현한 바인딩 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ae26e-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="ae26e-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="ae26e-113">CloseTimeout</span></span>  
 <span data-ttu-id="ae26e-114">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="ae26e-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="ae26e-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae26e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae26e-116">닫기 작업을 완료하기 위해 제공된 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="ae26e-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="ae26e-117">name</span><span class="sxs-lookup"><span data-stu-id="ae26e-117">Name</span></span>  
 <span data-ttu-id="ae26e-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="ae26e-118">Data type: string</span></span>  
  
 <span data-ttu-id="ae26e-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae26e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae26e-120">바인딩 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ae26e-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="ae26e-121">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="ae26e-121">Namespace</span></span>  
 <span data-ttu-id="ae26e-122">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="ae26e-122">Data type: string</span></span>  
  
 <span data-ttu-id="ae26e-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae26e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae26e-124">바인딩의 XML 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ae26e-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="ae26e-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="ae26e-125">OpenTimeout</span></span>  
 <span data-ttu-id="ae26e-126">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="ae26e-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="ae26e-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae26e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae26e-128">열기 작업을 완료하기 위해 제공된 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="ae26e-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="ae26e-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="ae26e-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="ae26e-130">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="ae26e-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="ae26e-131">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae26e-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae26e-132">받기 작업을 완료하기 위해 제공된 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="ae26e-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="ae26e-133">Scheme</span><span class="sxs-lookup"><span data-stu-id="ae26e-133">Scheme</span></span>  
 <span data-ttu-id="ae26e-134">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="ae26e-134">Data type: string</span></span>  
  
 <span data-ttu-id="ae26e-135">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae26e-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae26e-136">바인딩이 빌드한 채널 및 수신기 팩터리에서 사용하는 URI 전송 체계입니다.</span><span class="sxs-lookup"><span data-stu-id="ae26e-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="ae26e-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="ae26e-137">SendTimeout</span></span>  
 <span data-ttu-id="ae26e-138">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="ae26e-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="ae26e-139">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae26e-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae26e-140">보내기 작업을 완료하기 위해 제공된 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="ae26e-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae26e-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae26e-141">Requirements</span></span>  
  
|<span data-ttu-id="ae26e-142">MOF</span><span class="sxs-lookup"><span data-stu-id="ae26e-142">MOF</span></span>|<span data-ttu-id="ae26e-143">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae26e-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ae26e-144">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="ae26e-144">Namespace</span></span>|<span data-ttu-id="ae26e-145">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae26e-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae26e-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae26e-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>
