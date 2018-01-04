---
title: "인스턴스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ed0c4a6f13ddcafdb3a9a773be9cd3f017474ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="instances"></a><span data-ttu-id="71ea3-102">인스턴스</span><span class="sxs-lookup"><span data-stu-id="71ea3-102">Instances</span></span>
<span data-ttu-id="71ea3-103">카운터 이름: Instances</span><span class="sxs-lookup"><span data-stu-id="71ea3-103">Counter Name: Instances.</span></span>  
  
## <a name="description"></a><span data-ttu-id="71ea3-104">설명</span><span class="sxs-lookup"><span data-stu-id="71ea3-104">Description</span></span>  
 <span data-ttu-id="71ea3-105">현재 서비스에 포함된 인스턴스 컨텍스트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="71ea3-105">Number of instance contexts that the service currently contains.</span></span>  
  
 <span data-ttu-id="71ea3-106">대체로 인스턴스 컨텍스트 수는 인스턴스 수와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="71ea3-106">Most of the time, the number of instance contexts is identical to the number of instances.</span></span> <span data-ttu-id="71ea3-107">그러나 다음 시나리오는 이 규칙의 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="71ea3-107">However, the following scenarios are exception to this rule.</span></span>  
  
-   <span data-ttu-id="71ea3-108">서비스 메서드가 명시적으로 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="71ea3-108">A service method calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method explicitly.</span></span>  
  
-   <span data-ttu-id="71ea3-109"><xref:System.ServiceModel.ReleaseInstanceMode>가 <xref:System.ServiceModel.OperationBehaviorAttribute> 인스턴스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="71ea3-109">A <xref:System.ServiceModel.ReleaseInstanceMode> is applied to an <xref:System.ServiceModel.OperationBehaviorAttribute> instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ea3-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71ea3-110">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
