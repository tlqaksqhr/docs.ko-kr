---
title: IEnumRAWINPUTDEVIC:Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 644a8e724a280a8b23048a381a099acd6e655d2c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="b44ad-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="b44ad-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="b44ad-103">다음 열거 `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) 에서 반환 되는 열거자의 목록에서 구조 `rgelt` 열거 요소에서의 실제 수와 함께 `pceltFetched`합니다.</span><span class="sxs-lookup"><span data-stu-id="b44ad-103">Enumerates the next `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b44ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="b44ad-104">Syntax</span></span>  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b44ad-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b44ad-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="b44ad-106">[in] 수가 [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) 구조에 반환 된 `rgelt`합니다.</span><span class="sxs-lookup"><span data-stu-id="b44ad-106">[in] Number of [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="b44ad-107">[out] 열거된 RAWINPUTDEVICE 구조체를 수신할 celt 크기(또는 더 큰)의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b44ad-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="b44ad-108">[out] `rgelt`에 실제로 제공된 요소 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b44ad-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="b44ad-109">`NULL`가 1이면 호출자가 `rgelt`을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b44ad-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b44ad-110">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="b44ad-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="b44ad-111">HRESULT: 제공된 요소 수가 `celt`이면 S_OK이고, 그러지 않으면 S_FALSE입니다.</span><span class="sxs-lookup"><span data-stu-id="b44ad-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
