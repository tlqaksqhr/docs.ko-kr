---
title: "GetPublicKeyToken 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetPublicKeyToken
api_location: alink.dll
api_type: COM
f1_keywords: GetPublicKeyToken
helpviewer_keywords: GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5f41c8088f095802cf35239afab279d6324adb55
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="d5679-102">GetPublicKeyToken 메서드</span><span class="sxs-lookup"><span data-stu-id="d5679-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="d5679-103">지정 된 키 파일 또는 키 컨테이너에 대 한 공개 키 토큰을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d5679-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5679-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5679-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5679-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5679-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="d5679-106">키의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d5679-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="d5679-107">키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d5679-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="d5679-108">키 토큰이 저장 됩니다. 여기서는 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5679-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="d5679-109">으로 표시 되는 버퍼를 바이트 단위로 크기를 지정 `pvPublicKeyToken`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5679-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="d5679-110">반환 되 면 실제 사용 되는 바이트 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5679-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5679-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="d5679-111">Return Value</span></span>  
 <span data-ttu-id="d5679-112">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5679-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5679-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5679-113">Requirements</span></span>  
 <span data-ttu-id="d5679-114">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d5679-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5679-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5679-115">See Also</span></span>  
 [<span data-ttu-id="d5679-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5679-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d5679-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5679-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d5679-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="d5679-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
