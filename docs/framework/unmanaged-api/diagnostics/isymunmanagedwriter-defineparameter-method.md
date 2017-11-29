---
title: "ISymUnmanagedWriter::DefineParameter 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineParameter
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 166087a27d0aa7b100da563c25f7e5a52612ce50
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterdefineparameter-method"></a><span data-ttu-id="d6ccd-102">ISymUnmanagedWriter::DefineParameter 메서드</span><span class="sxs-lookup"><span data-stu-id="d6ccd-102">ISymUnmanagedWriter::DefineParameter Method</span></span>
<span data-ttu-id="d6ccd-103">현재 메서드의 단일 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ccd-103">Defines a single parameter in the current method.</span></span> <span data-ttu-id="d6ccd-104">메서드 시그니처 내에서 매개 변수 위치 (시퀀스)에서 매개 변수 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d6ccd-104">The parameter type is taken from the parameter's position (sequence) within the method's signature.</span></span>  
  
 <span data-ttu-id="d6ccd-105">매개 변수 지정된 메서드에 대 한 메타 데이터에 정의 된 경우이 방법을 사용 하 여 다시 정의할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6ccd-105">If parameters are defined in the metadata for a given method, you do not have to define them again by using this method.</span></span> <span data-ttu-id="d6ccd-106">기호 판독기 기호 저장소를 검사 하기 전에 매개 변수에 대 한 일반 메타 데이터를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ccd-106">The symbol readers must check the normal metadata for the parameters before checking the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6ccd-107">구문</span><span class="sxs-lookup"><span data-stu-id="d6ccd-107">Syntax</span></span>  
  
```  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6ccd-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d6ccd-108">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d6ccd-109">[in] 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ccd-109">[in] The parameter name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="d6ccd-110">[in] 매개 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ccd-110">[in] The parameter attributes.</span></span>  
  
 `sequence`  
 <span data-ttu-id="d6ccd-111">[in] 매개 변수 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ccd-111">[in] The parameter signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="d6ccd-112">[in] 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ccd-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="d6ccd-113">[in] 매개 변수 사양에 대 한 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ccd-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="d6ccd-114">[in] 매개 변수 사양에 대 한 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ccd-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="d6ccd-115">[in] 매개 변수 사양에 대 한 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ccd-115">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6ccd-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="d6ccd-116">Return Value</span></span>  
 <span data-ttu-id="d6ccd-117">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d6ccd-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6ccd-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6ccd-118">Requirements</span></span>  
 <span data-ttu-id="d6ccd-119">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d6ccd-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6ccd-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6ccd-120">See Also</span></span>  
 [<span data-ttu-id="d6ccd-121">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6ccd-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
