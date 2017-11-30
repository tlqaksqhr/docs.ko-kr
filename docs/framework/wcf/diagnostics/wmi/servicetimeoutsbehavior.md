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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d4b597dbdd8dfea1cab35c717f416d91677c5987
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="c6aa5-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="c6aa5-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="c6aa5-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="c6aa5-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6aa5-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6aa5-104">Syntax</span></span>  
  
```  
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c6aa5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c6aa5-105">Methods</span></span>  
 <span data-ttu-id="c6aa5-106">ServiceTimeoutsBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6aa5-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c6aa5-107">속성</span><span class="sxs-lookup"><span data-stu-id="c6aa5-107">Properties</span></span>  
 <span data-ttu-id="c6aa5-108">ServiceTimeoutsBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6aa5-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="c6aa5-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="c6aa5-109">TransactionTimeout</span></span>  
 <span data-ttu-id="c6aa5-110">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="c6aa5-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="c6aa5-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c6aa5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c6aa5-112">트랜잭션을 완료해야 하는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="c6aa5-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6aa5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c6aa5-113">Requirements</span></span>  
  
|<span data-ttu-id="c6aa5-114">MOF</span><span class="sxs-lookup"><span data-stu-id="c6aa5-114">MOF</span></span>|<span data-ttu-id="c6aa5-115">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6aa5-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c6aa5-116">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="c6aa5-116">Namespace</span></span>|<span data-ttu-id="c6aa5-117">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6aa5-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6aa5-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6aa5-118">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
