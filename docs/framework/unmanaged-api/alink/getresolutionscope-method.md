---
title: "GetResolutionScope 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetResolutionScope
api_location: alink.dll
api_type: COM
f1_keywords: GetResolutionScope
helpviewer_keywords: GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 11ccbce4d8e9783514050f6b41c6e32cde6c274f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="11735-102">GetResolutionScope 메서드</span><span class="sxs-lookup"><span data-stu-id="11735-102">GetResolutionScope Method</span></span>
<span data-ttu-id="11735-103">지정 된 형식의 범위를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="11735-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11735-104">구문</span><span class="sxs-lookup"><span data-stu-id="11735-104">Syntax</span></span>  
  
```  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="11735-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11735-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="11735-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="11735-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="11735-107">참조를 수행 해야 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="11735-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="11735-108">파일의 토큰 해당 형식이 정의 일반적으로 사용 하 여 검색 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11735-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="11735-109">어셈블리 또는 모듈 참조를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="11735-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11735-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="11735-110">Return Value</span></span>  
 <span data-ttu-id="11735-111">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="11735-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11735-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11735-112">Requirements</span></span>  
 <span data-ttu-id="11735-113">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="11735-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11735-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11735-114">See Also</span></span>  
 [<span data-ttu-id="11735-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11735-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="11735-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11735-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="11735-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="11735-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
