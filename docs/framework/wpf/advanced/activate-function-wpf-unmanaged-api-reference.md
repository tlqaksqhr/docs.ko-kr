---
title: "활성화 함수 (WPF 관리 되지 않는 API 참조)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: Acrivate
api_location: PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 68f3f2a29da11a648b8c635667de6493a04ccd54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="bbd39-102">활성화 함수 (WPF 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="bbd39-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="bbd39-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbd39-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="bbd39-104">Windows 관리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbd39-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbd39-105">구문</span><span class="sxs-lookup"><span data-stu-id="bbd39-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbd39-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bbd39-106">Parameters</span></span>  
 <span data-ttu-id="bbd39-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="bbd39-107">pParameters</span></span>  
 <span data-ttu-id="bbd39-108">활성화 매개 변수 창에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bbd39-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="bbd39-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="bbd39-109">ppInner</span></span>  
 <span data-ttu-id="bbd39-110">에 대 한 포인터를 포함 하는 단일 요소 버퍼의 주소에 대 한 포인터는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bbd39-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbd39-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bbd39-111">Requirements</span></span>  
 <span data-ttu-id="bbd39-112">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bbd39-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbd39-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="bbd39-113">**DLL:**</span></span>  
  
 <span data-ttu-id="bbd39-114">.NET framework 3.0 및 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="bbd39-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="bbd39-115">.NET Framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="bbd39-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="bbd39-116">**.NET framework 버전:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbd39-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbd39-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bbd39-117">See Also</span></span>  
 [<span data-ttu-id="bbd39-118">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="bbd39-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
