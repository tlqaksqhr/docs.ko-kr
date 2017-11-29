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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fd01c5c4d37f5c0ec5673dc9aa4a47cb8affbc29
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="ae272-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="ae272-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="ae272-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="ae272-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae272-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae272-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="ae272-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ae272-105">Methods</span></span>  
 <span data-ttu-id="ae272-106">OperationBehaviorAttribute 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae272-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ae272-107">속성</span><span class="sxs-lookup"><span data-stu-id="ae272-107">Properties</span></span>  
 <span data-ttu-id="ae272-108">OperationBehaviorAttribute 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae272-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="ae272-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="ae272-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="ae272-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="ae272-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="ae272-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae272-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae272-112">매개 변수에 대한 자동 삭제 기능 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="ae272-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="ae272-113">가장</span><span class="sxs-lookup"><span data-stu-id="ae272-113">Impersonation</span></span>  
 <span data-ttu-id="ae272-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="ae272-114">Data type: string</span></span>  
  
 <span data-ttu-id="ae272-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae272-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae272-116">작업에서 지원하는 호출자의 가장 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae272-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="ae272-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="ae272-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="ae272-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="ae272-118">Data type: string</span></span>  
  
 <span data-ttu-id="ae272-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae272-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae272-120">작업 과정에서 개체를 재활용하기 위해 호출하는 시점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae272-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="ae272-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="ae272-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="ae272-122">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="ae272-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="ae272-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae272-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae272-124">처리되지 않은 예외가 발생하지 않을 때 현재 트랜잭션을 자동으로 커밋할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae272-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="ae272-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="ae272-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="ae272-126">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="ae272-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="ae272-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="ae272-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ae272-128">작업에서 트랜잭션이 필요한지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae272-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae272-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae272-129">Requirements</span></span>  
  
|<span data-ttu-id="ae272-130">MOF</span><span class="sxs-lookup"><span data-stu-id="ae272-130">MOF</span></span>|<span data-ttu-id="ae272-131">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae272-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ae272-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="ae272-132">Namespace</span></span>|<span data-ttu-id="ae272-133">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae272-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae272-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae272-134">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
