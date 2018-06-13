---
title: SetManifestFile 메서드
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f8398c16b27836b772e8ac56ee1f7e8494f4be0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403571"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="9ba9e-102">SetManifestFile 메서드</span><span class="sxs-lookup"><span data-stu-id="9ba9e-102">SetManifestFile Method</span></span>
<span data-ttu-id="9ba9e-103">지정 하거나 어셈블리를 만들 때 링커에서 사용 하는 매니페스트 파일을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ba9e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9ba9e-104">Syntax</span></span>  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9ba9e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ba9e-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="9ba9e-106">콘텐츠가 Win32 리소스 blob에 저장 된 매니페스트 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ba9e-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="9ba9e-107">Return Value</span></span>  
 <span data-ttu-id="9ba9e-108">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ba9e-109">설명</span><span class="sxs-lookup"><span data-stu-id="9ba9e-109">Remarks</span></span>  
 <span data-ttu-id="9ba9e-110">Win32ResBlob를 요청 하기 전에이 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="9ba9e-111">값은 `pszFile` 매개 변수는 내용을 읽고 RT_MANIFEST의 ID를 사용 하 여 Win32 리소스에 매니페스트 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="9ba9e-112">NULL의 매개 변수를 사용 하 여를 호출할 때는 모든 이전에 읽은 매니페스트가 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="9ba9e-113">초기화 시에 링커의 상태를 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba9e-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ba9e-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ba9e-114">Requirements</span></span>  
 <span data-ttu-id="9ba9e-115">ALink.h 필요</span><span class="sxs-lookup"><span data-stu-id="9ba9e-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ba9e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ba9e-116">See Also</span></span>  
 [<span data-ttu-id="9ba9e-117">IALink3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ba9e-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)  
 [<span data-ttu-id="9ba9e-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="9ba9e-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [<span data-ttu-id="9ba9e-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ba9e-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="9ba9e-120">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="9ba9e-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
