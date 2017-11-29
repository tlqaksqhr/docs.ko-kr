---
title: "LoadFromHistory 함수 (WPF 관리 되지 않는 API 참조)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: LoadFromHistory
api_location: PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cdb68700ab0c11bbd6b09b83a826dc5ca4faa086
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="0bc4c-102">LoadFromHistory 함수 (WPF 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="0bc4c-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="0bc4c-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc4c-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="0bc4c-104">Windows 관리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc4c-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bc4c-105">구문</span><span class="sxs-lookup"><span data-stu-id="0bc4c-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0bc4c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0bc4c-106">Parameters</span></span>  
 <span data-ttu-id="0bc4c-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="0bc4c-107">pHistoryStream</span></span>  
 <span data-ttu-id="0bc4c-108">기록 정보 스트림에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc4c-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="0bc4c-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="0bc4c-109">pBindCtx</span></span>  
 <span data-ttu-id="0bc4c-110">바인딩 컨텍스트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc4c-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bc4c-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0bc4c-111">Requirements</span></span>  
 <span data-ttu-id="0bc4c-112">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc4c-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bc4c-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="0bc4c-113">**DLL:**</span></span>  
  
 <span data-ttu-id="0bc4c-114">.NET framework 3.0 및 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="0bc4c-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="0bc4c-115">.NET Framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="0bc4c-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="0bc4c-116">**.NET framework 버전:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bc4c-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bc4c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bc4c-117">See Also</span></span>  
 [<span data-ttu-id="0bc4c-118">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="0bc4c-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
