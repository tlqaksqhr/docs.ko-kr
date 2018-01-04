---
title: IEnumRAWINPUTDEVIC:Clone
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: db218ec824dfe163946b0c1bd412efd0f78f4ad8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="2f9b7-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="2f9b7-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="2f9b7-103">현재 열거자와 동일한 상태인 다른 원시 입력 장치 열거자를 만들어 동일한 목록을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9b7-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f9b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f9b7-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f9b7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f9b7-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="2f9b7-106">[out] 수신 하는 출력 변수의 주소는 [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2f9b7-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="2f9b7-107">메서드가 실패할 경우이 출력 변수의 값을 정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f9b7-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2f9b7-108">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="2f9b7-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="2f9b7-109">HRESULT:이 메서드는 표준 반환 값 E_INVALIDARG 및 E_OUTOFMEMORY와 E_UNEXPECTED를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9b7-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f9b7-110">설명</span><span class="sxs-lookup"><span data-stu-id="2f9b7-110">Remarks</span></span>  
 <span data-ttu-id="2f9b7-111">이 메서드를 사용 하면 나중에 해당 지점에 반환 하기 위해 한 지점을 열거 시퀀스에서 기록 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9b7-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="2f9b7-112">호출자에 게 첫 번째 열거자와는 별도로이 새로운 열거자를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f9b7-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
