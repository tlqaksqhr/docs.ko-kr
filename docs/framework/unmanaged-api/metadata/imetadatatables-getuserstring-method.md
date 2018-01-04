---
title: "IMetaDataTables::GetUserString 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetUserString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f3d7ffc2c7334a6b5873581bf9f079b2b7c8053e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="22cc3-102">IMetaDataTables::GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="22cc3-102">IMetaDataTables::GetUserString Method</span></span>
<span data-ttu-id="22cc3-103">현재 범위에서 문자열 열에서 지정된 된 인덱스에 하드 코드 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="22cc3-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22cc3-104">구문</span><span class="sxs-lookup"><span data-stu-id="22cc3-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
    [in]  ULONG       ixUserString,  
    [out] ULONG       *pcbData,  
    [out] const void  **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22cc3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="22cc3-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="22cc3-106">[in] 하드 코드 된 문자열을 검색할 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="22cc3-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="22cc3-107">[out] p;의 크기에 대 한 포인터 `ppData`합니다.</span><span class="sxs-lookup"><span data-stu-id="22cc3-107">[out] A p;ointer to the size of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="22cc3-108">[out] 반환 된 문자열에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="22cc3-108">[out] A pointer to a pointer to the returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22cc3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="22cc3-109">Requirements</span></span>  
 <span data-ttu-id="22cc3-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="22cc3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22cc3-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="22cc3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="22cc3-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="22cc3-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="22cc3-113">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22cc3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22cc3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22cc3-114">See Also</span></span>  
 [<span data-ttu-id="22cc3-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22cc3-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="22cc3-116">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="22cc3-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
