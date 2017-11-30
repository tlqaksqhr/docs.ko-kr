---
title: "IMetaDataImport::GetFieldMarshal 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetFieldMarshal
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce29990bf9e6b5b670a9a277442adac4ceef2947
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="e8d7b-102">IMetaDataImport::GetFieldMarshal 메서드</span><span class="sxs-lookup"><span data-stu-id="e8d7b-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="e8d7b-103">지정 된 필드 메타 데이터 토큰이 나타내는 필드의 관리 되지 않는 네이티브 형식에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e8d7b-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8d7b-104">구문</span><span class="sxs-lookup"><span data-stu-id="e8d7b-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8d7b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e8d7b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e8d7b-106">[in] Interop 마샬링 정보를 가져올 필드를 나타내는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e8d7b-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="e8d7b-107">[out] 메타 데이터 서명의 필드의 네이티브 형식에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e8d7b-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="e8d7b-108">[out] 바이트 크기 `ppvNativeType`합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d7b-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8d7b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8d7b-109">Requirements</span></span>  
 <span data-ttu-id="e8d7b-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d7b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8d7b-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e8d7b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8d7b-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e8d7b-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e8d7b-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8d7b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d7b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8d7b-114">See Also</span></span>  
 [<span data-ttu-id="e8d7b-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8d7b-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e8d7b-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8d7b-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
