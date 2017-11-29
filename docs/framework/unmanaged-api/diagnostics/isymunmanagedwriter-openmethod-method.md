---
title: "ISymUnmanagedWriter::OpenMethod 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 61d63fb96635e34e07c3997c1aad838e67c70742
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriteropenmethod-method"></a><span data-ttu-id="a4071-102">ISymUnmanagedWriter::OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="a4071-102">ISymUnmanagedWriter::OpenMethod Method</span></span>
<span data-ttu-id="a4071-103">에 기호 정보를 내보내지 메서드를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4071-103">Opens a method into which symbol information is emitted.</span></span> <span data-ttu-id="a4071-104">지정 된 메서드 시퀀스 위치, 매개 변수 및 어휘 범위를 정의 하는 호출에 대 한 현재 메서드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4071-104">The given method becomes the current method for calls to define sequence points, parameters, and lexical scopes.</span></span> <span data-ttu-id="a4071-105">전체 메서드 주위에 암시적 어휘 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4071-105">There is an implicit lexical scope around the entire method.</span></span> <span data-ttu-id="a4071-106">이전에 닫힌 하는 메서드를 다시 열면 해당 메서드에 대 한 모든 이전에 정의 된 기호를 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="a4071-106">Reopening a method that was previously closed erases any previously defined symbols for that method.</span></span> <span data-ttu-id="a4071-107">한 번에 하나의 open 메서드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4071-107">There can be only one open method at a time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4071-108">구문</span><span class="sxs-lookup"><span data-stu-id="a4071-108">Syntax</span></span>  
  
```  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4071-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4071-109">Parameters</span></span>  
 `method`  
 <span data-ttu-id="a4071-110">[in] 열릴 메서드의 대 한 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="a4071-110">[in] The metadata token for the method to be opened.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4071-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="a4071-111">Return Value</span></span>  
 <span data-ttu-id="a4071-112">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a4071-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4071-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4071-113">Requirements</span></span>  
 <span data-ttu-id="a4071-114">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a4071-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4071-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4071-115">See Also</span></span>  
 [<span data-ttu-id="a4071-116">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4071-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="a4071-117">CloseMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="a4071-117">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)  
 [<span data-ttu-id="a4071-118">OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="a4071-118">OpenMethod2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
