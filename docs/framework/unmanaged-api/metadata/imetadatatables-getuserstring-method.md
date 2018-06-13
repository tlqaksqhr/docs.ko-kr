---
title: IMetaDataTables::GetUserString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d7dee3da1967f8a958ea95ab4555f279c962f51
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451797"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="3aebd-102">IMetaDataTables::GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="3aebd-102">IMetaDataTables::GetUserString Method</span></span>
<span data-ttu-id="3aebd-103">현재 범위에서 문자열 열에서 지정된 된 인덱스에 하드 코드 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3aebd-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aebd-104">구문</span><span class="sxs-lookup"><span data-stu-id="3aebd-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
    [in]  ULONG       ixUserString,  
    [out] ULONG       *pcbData,  
    [out] const void  **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3aebd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3aebd-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="3aebd-106">[in] 하드 코드 된 문자열을 검색할 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3aebd-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="3aebd-107">[out] p;의 크기에 대 한 포인터 `ppData`합니다.</span><span class="sxs-lookup"><span data-stu-id="3aebd-107">[out] A p;ointer to the size of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="3aebd-108">[out] 반환 된 문자열에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3aebd-108">[out] A pointer to a pointer to the returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aebd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3aebd-109">Requirements</span></span>  
 <span data-ttu-id="3aebd-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3aebd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aebd-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3aebd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3aebd-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="3aebd-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3aebd-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3aebd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aebd-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3aebd-114">See Also</span></span>  
 [<span data-ttu-id="3aebd-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3aebd-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="3aebd-116">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3aebd-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
