---
title: EndMerge 메서드
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e8f9eecd6d6d74717eb7c1e389bfa24e40afc950
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402576"
---
# <a name="endmerge-method"></a><span data-ttu-id="9b8fd-102">EndMerge 메서드</span><span class="sxs-lookup"><span data-stu-id="9b8fd-102">EndMerge Method</span></span>
<span data-ttu-id="9b8fd-103">모든 사용자 지정 특성 내보내기 범위에 병합 된 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b8fd-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b8fd-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b8fd-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9b8fd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b8fd-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9b8fd-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9b8fd-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b8fd-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="9b8fd-107">Return Value</span></span>  
 <span data-ttu-id="9b8fd-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b8fd-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b8fd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9b8fd-109">Requirements</span></span>  
 <span data-ttu-id="9b8fd-110">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="9b8fd-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b8fd-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b8fd-111">See Also</span></span>  
 [<span data-ttu-id="9b8fd-112">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b8fd-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="9b8fd-113">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9b8fd-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="9b8fd-114">ALink API</span><span class="sxs-lookup"><span data-stu-id="9b8fd-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
