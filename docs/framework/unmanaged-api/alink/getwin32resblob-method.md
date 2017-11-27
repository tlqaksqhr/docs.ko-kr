---
title: "GetWin32ResBlob 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetWin32ResBlob
api_location: alink.dll
api_type: COM
f1_keywords: GetWin32ResBlob
helpviewer_keywords: GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9c4456757c56440463010d4adc3d3eed90dbc07a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="61252-102">GetWin32ResBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="61252-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="61252-103">Win32 리소스 blob를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="61252-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="61252-104">어셈블리 옵션을 설정한 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="61252-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61252-105">구문</span><span class="sxs-lookup"><span data-stu-id="61252-105">Syntax</span></span>  
  
```  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61252-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="61252-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="61252-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="61252-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="61252-108">Win32 버전 리소스를 생성할 때 사용할 파일 이름을 검색 하는 데 사용 되는 파일 토큰</span><span class="sxs-lookup"><span data-stu-id="61252-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="61252-109">파일은 DLL, false EXE에 대 한 경우 TRUE입니다.</span><span class="sxs-lookup"><span data-stu-id="61252-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="61252-110">Blob 리소스에 삽입할 선택적 아이콘입니다.</span><span class="sxs-lookup"><span data-stu-id="61252-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="61252-111">리소스 blob를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="61252-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="61252-112">Blob의 크기를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="61252-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61252-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="61252-113">Return Value</span></span>  
 <span data-ttu-id="61252-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="61252-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61252-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="61252-115">Requirements</span></span>  
 <span data-ttu-id="61252-116">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="61252-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61252-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61252-117">See Also</span></span>  
 [<span data-ttu-id="61252-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61252-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="61252-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="61252-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="61252-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="61252-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
