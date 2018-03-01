---
title: "ISymUnmanagedWriter::UsingNamespace 메서드"
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
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2d02a36a43e8a831fbbef051f5898696d4d8e04c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="1655e-102">ISymUnmanagedWriter::UsingNamespace 메서드</span><span class="sxs-lookup"><span data-stu-id="1655e-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="1655e-103">지정 된 정규화 된 네임 스페이스 이름이 열린 어휘 범위 내에서 사용량을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1655e-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="1655e-104">네임 스페이스는 현재 열려 범위에서 상속 되는 모든 범위 내에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1655e-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="1655e-105">현재 범위를 닫으면 네임 스페이스의 사용도 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1655e-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1655e-106">구문</span><span class="sxs-lookup"><span data-stu-id="1655e-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1655e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1655e-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="1655e-108">[in] 네임 스페이스의 정규화 된 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1655e-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1655e-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="1655e-109">Return Value</span></span>  
 <span data-ttu-id="1655e-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1655e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1655e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1655e-111">Requirements</span></span>  
 <span data-ttu-id="1655e-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1655e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1655e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1655e-113">See Also</span></span>  
 [<span data-ttu-id="1655e-114">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1655e-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
