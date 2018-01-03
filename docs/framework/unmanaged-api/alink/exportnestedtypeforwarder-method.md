---
title: "ExportNestedTypeForwarder 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportNestedTypeForwarder
api_location: alink.dll
api_type: COM
f1_keywords: ExportNestedTypeForwarder
helpviewer_keywords: ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eee41e9f71d600a74cc9f74b538ad9e215f0d905
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="e4f9b-102">ExportNestedTypeForwarder 메서드</span><span class="sxs-lookup"><span data-stu-id="e4f9b-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="e4f9b-103">지정된 된 어셈블리의 형식 테이블에 중첩 된 형식에 대 한 형식 전달자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4f9b-104">구문</span><span class="sxs-lookup"><span data-stu-id="e4f9b-104">Syntax</span></span>  
  
```  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4f9b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e4f9b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e4f9b-106">내보낼 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="e4f9b-107">파일 형식을 정의 하는 파일의 토큰 또는 어셈블리 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="e4f9b-108">토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="e4f9b-109">부모 유형의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="e4f9b-110">내보낼 정규화 된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e4f9b-111">`ComType`와 같은 플래그 `tdPublic` 또는 `tdNested`합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="e4f9b-112">내보내기 형식의 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-112">Receives token of export type.</span></span> <span data-ttu-id="e4f9b-113">이 중첩 된 형식을 내보내는에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4f9b-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="e4f9b-114">Return Value</span></span>  
 <span data-ttu-id="e4f9b-115">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f9b-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4f9b-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4f9b-116">Requirements</span></span>  
 <span data-ttu-id="e4f9b-117">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="e4f9b-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f9b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4f9b-118">See Also</span></span>  
 [<span data-ttu-id="e4f9b-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4f9b-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e4f9b-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4f9b-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e4f9b-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="e4f9b-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
