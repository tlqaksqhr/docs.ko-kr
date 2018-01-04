---
title: "IAssemblyCache::QueryAssemblyInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache.QueryAssemblyInfo
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66e09f805b120239eef764b8cd61835e713e236c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="c8ee2-102">IAssemblyCache::QueryAssemblyInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="c8ee2-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="c8ee2-103">지정된 된 어셈블리에 대 한 요청 된 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8ee2-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8ee2-104">구문</span><span class="sxs-lookup"><span data-stu-id="c8ee2-104">Syntax</span></span>  
  
```  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8ee2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8ee2-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="c8ee2-106">[in] 값에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="c8ee2-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="c8ee2-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8ee2-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="c8ee2-108">QUERYASMINFO_FLAG_VALIDATE (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="c8ee2-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
-   <span data-ttu-id="c8ee2-109">QUERYASMINFO_FLAG_GETSIZE (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="c8ee2-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="c8ee2-110">[in] 데이터 검색 되는 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c8ee2-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="c8ee2-111">[out에서] [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) 어셈블리에 대 한 데이터가 포함 된 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="c8ee2-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8ee2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8ee2-112">Requirements</span></span>  
 <span data-ttu-id="c8ee2-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c8ee2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8ee2-114">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c8ee2-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c8ee2-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8ee2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8ee2-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8ee2-116">See Also</span></span>  
 [<span data-ttu-id="c8ee2-117">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8ee2-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
