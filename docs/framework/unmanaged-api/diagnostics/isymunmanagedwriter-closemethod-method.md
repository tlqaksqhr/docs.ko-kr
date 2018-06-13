---
title: ISymUnmanagedWriter::CloseMethod 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71be697a8a1decd9b5f780d047c3dbb397e351d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426892"
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="0299e-102">ISymUnmanagedWriter::CloseMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="0299e-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="0299e-103">현재 메서드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0299e-103">Closes the current method.</span></span> <span data-ttu-id="0299e-104">메서드를 닫은 후 내에서 더 이상 없는 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0299e-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0299e-105">구문</span><span class="sxs-lookup"><span data-stu-id="0299e-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0299e-106">반환 값</span><span class="sxs-lookup"><span data-stu-id="0299e-106">Return Value</span></span>  
 <span data-ttu-id="0299e-107">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0299e-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0299e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0299e-108">Requirements</span></span>  
 <span data-ttu-id="0299e-109">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0299e-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0299e-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0299e-110">See Also</span></span>  
 [<span data-ttu-id="0299e-111">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0299e-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="0299e-112">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="0299e-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
