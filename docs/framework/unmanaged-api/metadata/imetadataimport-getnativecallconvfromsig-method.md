---
title: "IMetaDataImport::GetNativeCallConvFromSig 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 56c67ad76fb3a4ce5ab2d107ff59da7a932835b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="7eca3-102">IMetaDataImport::GetNativeCallConvFromSig 메서드</span><span class="sxs-lookup"><span data-stu-id="7eca3-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="7eca3-103">지정한 서명 포인터가 나타내는 메서드에 대한 기본 호출 규칙을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7eca3-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eca3-104">구문</span><span class="sxs-lookup"><span data-stu-id="7eca3-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7eca3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7eca3-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="7eca3-106">[in] 에 대 한 호출 규칙을 반환 하는 메서드의 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7eca3-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="7eca3-107">[in] 바이트 크기 `pvSig`합니다.</span><span class="sxs-lookup"><span data-stu-id="7eca3-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="7eca3-108">[out] 네이티브 호출 규칙에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7eca3-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eca3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7eca3-109">Requirements</span></span>  
 <span data-ttu-id="7eca3-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7eca3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eca3-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7eca3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7eca3-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7eca3-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7eca3-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eca3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eca3-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7eca3-114">See Also</span></span>  
 <xref:System.Runtime.InteropServices.CallingConvention>  
 [<span data-ttu-id="7eca3-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7eca3-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="7eca3-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7eca3-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
