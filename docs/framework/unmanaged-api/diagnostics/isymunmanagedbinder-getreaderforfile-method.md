---
title: "ISymUnmanagedBinder::GetReaderForFile 메서드"
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
- ISymUnmanagedBinder.GetReaderForFile
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9c50bb4ca36043fc2491c9a0615b682c94c422e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="a5ef0-102">ISymUnmanagedBinder::GetReaderForFile 메서드</span><span class="sxs-lookup"><span data-stu-id="a5ef0-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="a5ef0-103">메타 데이터 인터페이스와 파일 이름을 제공 올바른 반환 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 구조는 모듈에 연결 된 디버깅 기호는 읽기입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ef0-103">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="a5ef0-104">이 메서드는 실행 파일 옆에 있는 경우에 프로그램 데이터베이스 (PDB) 파일을 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a5ef0-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="a5ef0-105">보안을 위해이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5ef0-105">This change has been made for security purposes.</span></span> <span data-ttu-id="a5ef0-106">PDB 파일에 대 한 보다 광범위 한 검색 해야 할 경우 사용 된 [isymunmanagedbinder2:: Getreaderforfile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="a5ef0-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5ef0-107">구문</span><span class="sxs-lookup"><span data-stu-id="a5ef0-107">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5ef0-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5ef0-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="a5ef0-109">[in] 메타 데이터 가져오기 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ef0-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="a5ef0-110">[in] 파일 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ef0-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="a5ef0-111">[in] 검색 경로에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ef0-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="a5ef0-112">[out] 설정 된 포인터가 반환 된 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ef0-112">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5ef0-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="a5ef0-113">Return Value</span></span>  
 <span data-ttu-id="a5ef0-114">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a5ef0-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5ef0-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5ef0-115">Requirements</span></span>  
 <span data-ttu-id="a5ef0-116">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a5ef0-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ef0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5ef0-117">See Also</span></span>  
 [<span data-ttu-id="a5ef0-118">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5ef0-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="a5ef0-119">GetReaderForFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="a5ef0-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
