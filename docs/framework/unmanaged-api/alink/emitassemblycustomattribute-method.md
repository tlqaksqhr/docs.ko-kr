---
title: "EmitAssemblyCustomAttribute 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location: alink.dll
api_type: COM
f1_keywords: EmitAssemblyCustomAttribute
helpviewer_keywords: EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb21ee1396a9dd0426b9b91711c2345ef66c09f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="44970-102">EmitAssemblyCustomAttribute 메서드</span><span class="sxs-lookup"><span data-stu-id="44970-102">EmitAssemblyCustomAttribute Method</span></span>
<span data-ttu-id="44970-103">호출 어셈블리 수준의 사용자 지정 특성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44970-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44970-104">구문</span><span class="sxs-lookup"><span data-stu-id="44970-104">Syntax</span></span>  
  
```  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44970-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44970-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="44970-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="44970-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="44970-107">특성을 정의 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="44970-107">File that defiles the attribute.</span></span> <span data-ttu-id="44970-108">경우 NULL이 될 수 `AssemblyID` 바인딩되지 않은 어셈블리를 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44970-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="44970-109">사용자 지정 특성의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="44970-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="44970-110">데이터 사용자 지정 값입니다.</span><span class="sxs-lookup"><span data-stu-id="44970-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="44970-111">사용자 지정 값 데이터의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="44970-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="44970-112">사용자 지정 특성은 어셈블리 서명을에 연결 하는 경우 TRUE입니다.</span><span class="sxs-lookup"><span data-stu-id="44970-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="44970-113">TRUE 이면 특성이 여러 개를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44970-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="44970-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="44970-114">Return Value</span></span>  
 <span data-ttu-id="44970-115">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="44970-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44970-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44970-116">Requirements</span></span>  
 <span data-ttu-id="44970-117">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="44970-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44970-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44970-118">See Also</span></span>  
 [<span data-ttu-id="44970-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44970-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="44970-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44970-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="44970-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="44970-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
