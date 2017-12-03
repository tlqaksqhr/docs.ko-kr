---
title: ActivityTransfer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c1caf0ae27efce858328e5db88434253be61d50
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="activitytransfer"></a><span data-ttu-id="5510c-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="5510c-102">ActivityTransfer</span></span>
<span data-ttu-id="5510c-103">활동 전송 이벤트</span><span class="sxs-lookup"><span data-stu-id="5510c-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5510c-104">구문</span><span class="sxs-lookup"><span data-stu-id="5510c-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5510c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5510c-105">Methods</span></span>  
 <span data-ttu-id="5510c-106">ActivityTransfer 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5510c-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5510c-107">속성</span><span class="sxs-lookup"><span data-stu-id="5510c-107">Properties</span></span>  
 <span data-ttu-id="5510c-108">ActivityTransfer 클래스에는 다음 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5510c-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="5510c-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="5510c-109">ActivityID</span></span>  
  
-   <span data-ttu-id="5510c-110">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="5510c-110">Data type: object</span></span>  
    <span data-ttu-id="5510c-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5510c-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="5510c-112">활동 ID</span><span class="sxs-lookup"><span data-stu-id="5510c-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="5510c-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="5510c-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="5510c-114">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="5510c-114">Data type: object</span></span>  
    <span data-ttu-id="5510c-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="5510c-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="5510c-116">관련 활동 ID</span><span class="sxs-lookup"><span data-stu-id="5510c-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5510c-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5510c-117">Requirements</span></span>  
  
|<span data-ttu-id="5510c-118">MOF</span><span class="sxs-lookup"><span data-stu-id="5510c-118">MOF</span></span>|<span data-ttu-id="5510c-119">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5510c-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5510c-120">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="5510c-120">Namespace</span></span>|<span data-ttu-id="5510c-121">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5510c-121">Defined in root\ServiceModel.</span></span>|
