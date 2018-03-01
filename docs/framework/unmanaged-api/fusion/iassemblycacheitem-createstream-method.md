---
title: "IAssemblyCacheItem::CreateStream 메서드"
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
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAsssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a24d9732a8e413b3cde0ac1c622743153ff6fd01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="3082f-102">IAssemblyCacheItem::CreateStream 메서드</span><span class="sxs-lookup"><span data-stu-id="3082f-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="3082f-103">지정 된 이름 및 형식 스트림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3082f-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3082f-104">구문</span><span class="sxs-lookup"><span data-stu-id="3082f-104">Syntax</span></span>  
  
```  
HRESULT CreateStream (  
    [in]  DWORD dwFlags,  
    [in]  LPCWSTR pszStreamName,  
    [in]  DWORD dwFormat,  
    [in]  DWORD dwFormatFlags,  
    [out] IStream **ppIStream,  
    [in, optional] ULARGE_INTEGER *puliMaxSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3082f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3082f-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="3082f-106">[in] 값에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="3082f-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="3082f-107">[in] 만들 스트림의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3082f-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="3082f-108">[in] 스트리밍할 수 파일의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3082f-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="3082f-109">[in] 값에 정의 된 형식에 따른 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="3082f-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="3082f-110">[out] 반환 된 주소에 대 한 포인터 <xref:IStream> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3082f-110">[out] A pointer to the address of the returned <xref:IStream> instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="3082f-111">[in, 선택 사항] 참조 하는 스트림의의 최대 크기 `ppIStream`합니다.</span><span class="sxs-lookup"><span data-stu-id="3082f-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3082f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3082f-112">Requirements</span></span>  
 <span data-ttu-id="3082f-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3082f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3082f-114">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="3082f-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3082f-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3082f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3082f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3082f-116">See Also</span></span>  
 [<span data-ttu-id="3082f-117">IAssemblyCacheItem 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3082f-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
