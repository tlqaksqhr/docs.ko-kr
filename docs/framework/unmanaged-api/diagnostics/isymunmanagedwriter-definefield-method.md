---
title: "ISymUnmanagedWriter::DefineField 메서드"
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
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 51adddc6a8e58846ebefe3c130adaa670c8351e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="ac59a-102">ISymUnmanagedWriter::DefineField 메서드</span><span class="sxs-lookup"><span data-stu-id="ac59a-102">ISymUnmanagedWriter::DefineField Method</span></span>
<span data-ttu-id="ac59a-103">메서드에 포함 되지 않는 단일 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac59a-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="ac59a-104">이 방법은 클래스의 특정 필드, 비트 필드 등에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac59a-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac59a-105">구문</span><span class="sxs-lookup"><span data-stu-id="ac59a-105">Syntax</span></span>  
  
```  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac59a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ac59a-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="ac59a-107">[in] 메타 데이터 형식 또는 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ac59a-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="ac59a-108">[in] 필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ac59a-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="ac59a-109">[in] 필드 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ac59a-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="ac59a-110">[in] A `ULONG32` 문자 필드 시그니처를 포함 하는 데 필요한 버퍼 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ac59a-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="ac59a-111">[in] 필드 시그니처에의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ac59a-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="ac59a-112">[in] 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ac59a-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="ac59a-113">[in] 필드 사양에 대 한 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ac59a-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="ac59a-114">[in] 필드 사양에 대 한 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ac59a-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="ac59a-115">[in] 필드 사양에 대 한 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ac59a-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac59a-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="ac59a-116">Return Value</span></span>  
 <span data-ttu-id="ac59a-117">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ac59a-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac59a-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac59a-118">Requirements</span></span>  
 <span data-ttu-id="ac59a-119">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ac59a-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac59a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac59a-120">See Also</span></span>  
 [<span data-ttu-id="ac59a-121">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac59a-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
