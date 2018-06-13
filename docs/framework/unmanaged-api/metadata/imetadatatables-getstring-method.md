---
title: IMetaDataTables::GetString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ed3501930b94eae59cf38355f8255ecf4165bcc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449584"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="9bf2a-102">IMetaDataTables::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="9bf2a-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="9bf2a-103">현재 참조 범위에서 테이블 열에서 지정된 된 인덱스에 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bf2a-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bf2a-104">구문</span><span class="sxs-lookup"><span data-stu-id="9bf2a-104">Syntax</span></span>  
  
```  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bf2a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9bf2a-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="9bf2a-106">[in] 다음 값을 검색할 시작 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf2a-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="9bf2a-107">[out] 반환 된 문자열 값에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf2a-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bf2a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bf2a-108">Requirements</span></span>  
 <span data-ttu-id="9bf2a-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9bf2a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bf2a-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9bf2a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9bf2a-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="9bf2a-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9bf2a-112">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bf2a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bf2a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bf2a-113">See Also</span></span>  
 [<span data-ttu-id="9bf2a-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9bf2a-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="9bf2a-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9bf2a-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
