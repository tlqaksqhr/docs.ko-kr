---
title: EmitAssembly 메서드
ms.date: 03/30/2017
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1cd1c077a8f2a5fe3b2b46c2e1da2e92b5a797a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402059"
---
# <a name="emitassembly-method"></a><span data-ttu-id="e41b2-102">EmitAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="e41b2-102">EmitAssembly Method</span></span>
<span data-ttu-id="e41b2-103">어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e41b2-103">Creates the assembly.</span></span> <span data-ttu-id="e41b2-104">어셈블리 파일을 제외한 다른 모든 파일이 닫혀 후이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41b2-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="e41b2-105">바인딩되지 않은 모듈을 만들 때이 메서드를 호출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e41b2-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e41b2-106">구문</span><span class="sxs-lookup"><span data-stu-id="e41b2-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e41b2-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e41b2-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e41b2-108">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e41b2-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e41b2-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="e41b2-109">Return Value</span></span>  
 <span data-ttu-id="e41b2-110">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e41b2-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e41b2-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e41b2-111">Requirements</span></span>  
 <span data-ttu-id="e41b2-112">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="e41b2-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e41b2-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e41b2-113">See Also</span></span>  
 [<span data-ttu-id="e41b2-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e41b2-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e41b2-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e41b2-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e41b2-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="e41b2-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
