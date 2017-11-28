---
title: "SetPEKind 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.SetPEKind
api_location: alink.dll
api_type: COM
f1_keywords: SetPEKind
helpviewer_keywords: SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d511bcda2ab4e879c123d866b3f6c887173c1d2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="setpekind-method"></a><span data-ttu-id="50f9d-102">SetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="50f9d-102">SetPEKind Method</span></span>
<span data-ttu-id="50f9d-103">이식 가능한 실행 파일 유형 컴퓨터 관련 되지 않거나 알 수 없는 컴퓨터를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="50f9d-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50f9d-104">구문</span><span class="sxs-lookup"><span data-stu-id="50f9d-104">Syntax</span></span>  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="50f9d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="50f9d-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="50f9d-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="50f9d-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="50f9d-107">토큰 PE 형식을 설정할 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="50f9d-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="50f9d-108">경우 NULL이 될 수 `AssemblyID` 바인딩되지 않은 어셈블리를 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50f9d-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="50f9d-109">PE에 표시 된 대로 형식은 [CorPEKind 열거형](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="50f9d-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="50f9d-110">대상 컴퓨터 아키텍처를 NT 헤더에 표시 된 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="50f9d-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50f9d-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="50f9d-111">Return Value</span></span>  
 <span data-ttu-id="50f9d-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="50f9d-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50f9d-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="50f9d-113">Requirements</span></span>  
 <span data-ttu-id="50f9d-114">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="50f9d-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50f9d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50f9d-115">See Also</span></span>  
 [<span data-ttu-id="50f9d-116">GetPEKind 메서드</span><span class="sxs-lookup"><span data-stu-id="50f9d-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)  
 [<span data-ttu-id="50f9d-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="50f9d-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="50f9d-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="50f9d-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="50f9d-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="50f9d-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
