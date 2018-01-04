---
title: IEnumRAWINPUTDEVICE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a93458e97ef317c425f3b51b1e3abc20ade2931b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="38438-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="38438-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="38438-103">이 인터페이스는 원시 입력 장치를 열거하며 PresentationHost.exe에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="38438-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38438-104">이 API는 로컬 클라이언트 컴퓨터에서만 사용할 수 있도록 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="38438-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="38438-105">멤버</span><span class="sxs-lookup"><span data-stu-id="38438-105">Members</span></span>  
  
|<span data-ttu-id="38438-106">멤버</span><span class="sxs-lookup"><span data-stu-id="38438-106">Member</span></span>|<span data-ttu-id="38438-107">설명</span><span class="sxs-lookup"><span data-stu-id="38438-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38438-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="38438-108">IEnumRAWINPUTDEVIC:Next</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)|<span data-ttu-id="38438-109">열거자 목록에서 다음 `celt` 요소(즉, RAWINPUTDEVICE 구조체)를 열거하고 `rgelt`의 실제 열거된 요소 수와 함께 `pceltFetched`에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="38438-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="38438-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="38438-110">IEnumRAWINPUTDEVIC:Skip</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-skip.md)|<span data-ttu-id="38438-111">열거자를 다음 건너뛰려면 지시 `celt` 열거형의 요소를 다음에 호출할 수 있도록 [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) 이러한 요소를 반환 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="38438-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="38438-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="38438-112">IEnumRAWINPUTDEVIC:Reset</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-reset.md)|<span data-ttu-id="38438-113">열거형 시퀀스를 시작 부분으로 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="38438-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="38438-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="38438-114">IEnumRAWINPUTDEVIC:Clone</span></span>](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-clone.md)|<span data-ttu-id="38438-115">현재 열거자와 동일한 상태인 다른 원시 입력 장치 열거자를 만들어 동일한 목록을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="38438-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38438-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38438-116">See Also</span></span>  
 [<span data-ttu-id="38438-117">원시 입력에 대 한</span><span class="sxs-lookup"><span data-stu-id="38438-117">About Raw Input</span></span>](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/aboutrawinput.asp)
