---
title: ServiceTimeoutsBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a65104a6fe76c22fca308091cc02e9496912129c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="8a12a-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="8a12a-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="8a12a-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="8a12a-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a12a-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a12a-104">Syntax</span></span>  
  
```  
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8a12a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8a12a-105">Methods</span></span>  
 <span data-ttu-id="8a12a-106">ServiceTimeoutsBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a12a-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8a12a-107">속성</span><span class="sxs-lookup"><span data-stu-id="8a12a-107">Properties</span></span>  
 <span data-ttu-id="8a12a-108">ServiceTimeoutsBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a12a-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="8a12a-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="8a12a-109">TransactionTimeout</span></span>  
 <span data-ttu-id="8a12a-110">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="8a12a-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="8a12a-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="8a12a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8a12a-112">트랜잭션을 완료해야 하는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="8a12a-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a12a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a12a-113">Requirements</span></span>  
  
|<span data-ttu-id="8a12a-114">MOF</span><span class="sxs-lookup"><span data-stu-id="8a12a-114">MOF</span></span>|<span data-ttu-id="8a12a-115">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a12a-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8a12a-116">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="8a12a-116">Namespace</span></span>|<span data-ttu-id="8a12a-117">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a12a-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a12a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a12a-118">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
