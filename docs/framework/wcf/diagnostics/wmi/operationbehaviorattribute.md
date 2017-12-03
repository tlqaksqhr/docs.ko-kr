---
title: OperationBehaviorAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: da0bc2ac9a4283ec9b23a1d4767f664de071ef47
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="b081a-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="b081a-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="b081a-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="b081a-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b081a-104">구문</span><span class="sxs-lookup"><span data-stu-id="b081a-104">Syntax</span></span>  
  
```  
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b081a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b081a-105">Methods</span></span>  
 <span data-ttu-id="b081a-106">OperationBehaviorAttribute 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b081a-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b081a-107">속성</span><span class="sxs-lookup"><span data-stu-id="b081a-107">Properties</span></span>  
 <span data-ttu-id="b081a-108">OperationBehaviorAttribute 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b081a-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="b081a-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="b081a-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="b081a-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="b081a-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="b081a-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="b081a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b081a-112">매개 변수에 대한 자동 삭제 기능 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="b081a-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="b081a-113">가장</span><span class="sxs-lookup"><span data-stu-id="b081a-113">Impersonation</span></span>  
 <span data-ttu-id="b081a-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="b081a-114">Data type: string</span></span>  
  
 <span data-ttu-id="b081a-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="b081a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b081a-116">작업에서 지원하는 호출자의 가장 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b081a-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="b081a-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="b081a-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="b081a-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="b081a-118">Data type: string</span></span>  
  
 <span data-ttu-id="b081a-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="b081a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b081a-120">작업 과정에서 개체를 재활용하기 위해 호출하는 시점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b081a-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="b081a-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="b081a-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="b081a-122">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="b081a-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="b081a-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="b081a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b081a-124">처리되지 않은 예외가 발생하지 않을 때 현재 트랜잭션을 자동으로 커밋할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b081a-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="b081a-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="b081a-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="b081a-126">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="b081a-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="b081a-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="b081a-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b081a-128">작업에서 트랜잭션이 필요한지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b081a-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b081a-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b081a-129">Requirements</span></span>  
  
|<span data-ttu-id="b081a-130">MOF</span><span class="sxs-lookup"><span data-stu-id="b081a-130">MOF</span></span>|<span data-ttu-id="b081a-131">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b081a-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b081a-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="b081a-132">Namespace</span></span>|<span data-ttu-id="b081a-133">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b081a-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b081a-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b081a-134">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
