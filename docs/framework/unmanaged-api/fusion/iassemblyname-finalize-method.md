---
title: IAssemblyName::Finalize 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.Finalize
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::Finalize
helpviewer_keywords:
- Finalize method [.NET Framework fusion]
- IAssemblyName::Finalize method [.NET Framework fusion]
ms.assetid: 610e792d-98ef-411f-90b0-5b9a3813f547
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 736b9efa1abf0c8ce10d15465b1742879db04ab7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428178"
---
# <a name="iassemblynamefinalize-method"></a><span data-ttu-id="cc378-102">IAssemblyName::Finalize 메서드</span><span class="sxs-lookup"><span data-stu-id="cc378-102">IAssemblyName::Finalize Method</span></span>
<span data-ttu-id="cc378-103">이러한 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 리소스를 해제 하 고 소멸자가 호출 되기 전에 다른 정리 작업을 수행할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cc378-103">Allows this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object to release resources and perform other cleanup operations before its destructor is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc378-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc378-104">Syntax</span></span>  
  
```  
HRESULT Finalize ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="cc378-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc378-105">Requirements</span></span>  
 <span data-ttu-id="cc378-106">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cc378-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc378-107">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="cc378-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cc378-108">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc378-108">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc378-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc378-109">See Also</span></span>  
 [<span data-ttu-id="cc378-110">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc378-110">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
