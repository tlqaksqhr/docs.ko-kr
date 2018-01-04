---
title: "ISymUnmanagedBinder2::GetReaderForFile2 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder2.GetReaderForFile2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 270a154c40b85ad4774bececf12685393f4d6c58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="9e31c-102">ISymUnmanagedBinder2::GetReaderForFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="9e31c-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="9e31c-103">메타 데이터 인터페이스와 파일 이름을 제공 올바른 반환 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 인터페이스를 모듈와 관련 된 디버깅 기호를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-103">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="9e31c-104">이 방법은 보다 프로그램 데이터베이스 (PDB) 파일에 대 한 보다 광범위 한 검색을 제공 된 [isymunmanagedbinder:: Getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="9e31c-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e31c-105">구문</span><span class="sxs-lookup"><span data-stu-id="9e31c-105">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e31c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e31c-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="9e31c-107">[in] 메타 데이터 가져오기 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="9e31c-108">[in] 파일 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="9e31c-109">[in] 검색 경로에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="9e31c-110">[in] 값은 [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) 기호 판독기에 대 한 검색을 수행할 때 사용할 정책을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="9e31c-111">[out] 설정 된 포인터가 반환 된 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-111">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e31c-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="9e31c-112">Return Value</span></span>  
 <span data-ttu-id="9e31c-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e31c-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e31c-114">Requirements</span></span>  
 <span data-ttu-id="9e31c-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9e31c-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e31c-116">설명</span><span class="sxs-lookup"><span data-stu-id="9e31c-116">Remarks</span></span>  
 <span data-ttu-id="9e31c-117">이 버전의 메서드 오른쪽 모듈에 있지 않은 영역에서 PDB 파일을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="9e31c-118">검색 정책 결합 하 여 제어할 수 있습니다 [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="9e31c-119">예를 들어 `AllowReferencePathAccess | AllowSymbolServerAccess` 옆에 있는 실행 파일 및 기호 서버에서 pdb 되지만 않습니다 레지스트리 나 실행 파일의 경로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="9e31c-120">경우는 `searchPath` 매개 변수를 제공,이 디렉터리는 항상 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e31c-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e31c-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e31c-121">See Also</span></span>  
 [<span data-ttu-id="9e31c-122">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e31c-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="9e31c-123">GetReaderForFile 메서드</span><span class="sxs-lookup"><span data-stu-id="9e31c-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
