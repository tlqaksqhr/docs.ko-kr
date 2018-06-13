---
title: ISymUnmanagedVariable::GetAddressField1 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f9e0e234a8f77ef35ad93302fe8fc676cf9dbaeb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427492"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="97117-102">ISymUnmanagedVariable::GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="97117-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="97117-103">이 변수에 대 한 첫 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="97117-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="97117-104">해당 의미 주소의 종류에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="97117-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97117-105">구문</span><span class="sxs-lookup"><span data-stu-id="97117-105">Syntax</span></span>  
  
```  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97117-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97117-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="97117-107">[out] 에 대 한 포인터는 `ULONG32` 받는 첫 번째 주소 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="97117-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97117-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="97117-108">Return Value</span></span>  
 <span data-ttu-id="97117-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="97117-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97117-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97117-110">Requirements</span></span>  
 <span data-ttu-id="97117-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="97117-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97117-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97117-112">See Also</span></span>  
 [<span data-ttu-id="97117-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97117-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="97117-114">GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="97117-114">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)  
 [<span data-ttu-id="97117-115">GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="97117-115">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)  
 [<span data-ttu-id="97117-116">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="97117-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)
