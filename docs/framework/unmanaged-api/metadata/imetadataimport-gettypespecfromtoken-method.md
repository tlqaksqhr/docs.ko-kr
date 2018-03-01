---
title: "IMetaDataImport::GetTypeSpecFromToken 메서드"
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
- IMetaDataImport.GetTypeSpecFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 10d4d9dcad2494410cc361617d5292c519b6dc00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="704c5-102">IMetaDataImport::GetTypeSpecFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="704c5-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="704c5-103">지정한 토큰이 나타내는 형식 사양의 이진 메타데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="704c5-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="704c5-104">구문</span><span class="sxs-lookup"><span data-stu-id="704c5-104">Syntax</span></span>  
  
```  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="704c5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="704c5-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="704c5-106">[in] 요청 된 메타 데이터 서명과 연결 된 TypeSpec 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="704c5-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="704c5-107">[out] 이진 메타 데이터 서명에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="704c5-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="704c5-108">[out] 메타 데이터 서명의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="704c5-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="704c5-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="704c5-109">Return Value</span></span>  
 <span data-ttu-id="704c5-110">성공 또는 실패를 나타내는 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="704c5-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="704c5-111">FAILED 매크로와 오류를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="704c5-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="704c5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="704c5-112">Requirements</span></span>  
 <span data-ttu-id="704c5-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="704c5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="704c5-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="704c5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="704c5-115">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="704c5-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="704c5-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="704c5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="704c5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="704c5-117">See Also</span></span>  
 [<span data-ttu-id="704c5-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="704c5-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="704c5-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="704c5-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
