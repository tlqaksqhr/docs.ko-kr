---
title: ISymUnmanagedVariable::GetAddressField3 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd474c7f149b8eff542b674c2ba6527b6a0cbcb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427000"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="d25f5-102">ISymUnmanagedVariable::GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="d25f5-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="d25f5-103">이 변수에 대 한 세 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="d25f5-104">해당 의미 주소의 종류에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d25f5-105">구문</span><span class="sxs-lookup"><span data-stu-id="d25f5-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d25f5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d25f5-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d25f5-107">[out] 에 대 한 포인터는 `ULONG32` 세 번째 필드에 주소를 받는입니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d25f5-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="d25f5-108">Return Value</span></span>  
 <span data-ttu-id="d25f5-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d25f5-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d25f5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d25f5-110">Requirements</span></span>  
 <span data-ttu-id="d25f5-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d25f5-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d25f5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d25f5-112">See Also</span></span>  
 [<span data-ttu-id="d25f5-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d25f5-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="d25f5-114">GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="d25f5-114">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)  
 [<span data-ttu-id="d25f5-115">GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="d25f5-115">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="d25f5-116">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="d25f5-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
