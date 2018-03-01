---
title: "ISymUnmanagedWriter::SetUserEntryPoint 메서드"
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
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5da021bce46df02789547eb7ee50133b6f4d4af6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="1abed-102">ISymUnmanagedWriter::SetUserEntryPoint 메서드</span><span class="sxs-lookup"><span data-stu-id="1abed-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="1abed-103">이 모듈에 대 한 진입점인 사용자 정의 메서드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1abed-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="1abed-104">예를 들어이 진입점에는 컴파일러에서 생성 된 스텁이 main 전에 대신 사용자의 주 방법일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1abed-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1abed-105">구문</span><span class="sxs-lookup"><span data-stu-id="1abed-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1abed-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1abed-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="1abed-107">[in] 사용자 진입점인 메서드의 메타 데이터 토큰을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="1abed-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1abed-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="1abed-108">Return Value</span></span>  
 <span data-ttu-id="1abed-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1abed-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1abed-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1abed-110">Requirements</span></span>  
 <span data-ttu-id="1abed-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1abed-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1abed-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1abed-112">See Also</span></span>  
 [<span data-ttu-id="1abed-113">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1abed-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
