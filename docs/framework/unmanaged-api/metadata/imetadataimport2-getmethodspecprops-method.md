---
title: "IMetaDataImport2::GetMethodSpecProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetMethodSpecProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b07e79f3990782e18ffdc57e9bd75a0b62765ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="307eb-102">IMetaDataImport2::GetMethodSpecProps 메서드</span><span class="sxs-lookup"><span data-stu-id="307eb-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="307eb-103">토큰을 지정 된 MethodSpec 참조 메서드의 메타 데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="307eb-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="307eb-104">구문</span><span class="sxs-lookup"><span data-stu-id="307eb-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="307eb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="307eb-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="307eb-106">[in] MethodSpec 토큰 방법의 인스턴스화를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="307eb-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="307eb-107">[out] 메서드 정의 나타내는 MethodDef 또는 MethodRef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="307eb-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="307eb-108">[out] 이진 메타 데이터 서명 메서드의 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="307eb-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="307eb-109">[out] 를 바이트 단위로 크기의 `ppvSigBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="307eb-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="307eb-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="307eb-110">Requirements</span></span>  
 <span data-ttu-id="307eb-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="307eb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="307eb-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="307eb-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="307eb-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="307eb-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="307eb-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="307eb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="307eb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="307eb-115">See Also</span></span>  
 [<span data-ttu-id="307eb-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="307eb-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="307eb-117">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="307eb-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
