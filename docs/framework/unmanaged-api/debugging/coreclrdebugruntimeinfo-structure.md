---
title: "CoreClrDebugRuntimeInfo 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoreClrDebugRuntimeInfo
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: effcc44b3f3b0926c1d711955fa77aa3e71a1592
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="c19d3-102">CoreClrDebugRuntimeInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="c19d3-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="c19d3-103">원격 컴퓨터의 프로세스에서 로드된 CLR(공용 언어 런타임) 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c19d3-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c19d3-104">구문</span><span class="sxs-lookup"><span data-stu-id="c19d3-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="c19d3-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c19d3-105">Members</span></span>  
  
|<span data-ttu-id="c19d3-106">멤버</span><span class="sxs-lookup"><span data-stu-id="c19d3-106">Member</span></span>|<span data-ttu-id="c19d3-107">설명</span><span class="sxs-lookup"><span data-stu-id="c19d3-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="c19d3-108">대상 컴퓨터에서 실행되는 원격 디버깅 프록시에 의해 할당된 런타임 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c19d3-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c19d3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c19d3-109">Requirements</span></span>  
 <span data-ttu-id="c19d3-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c19d3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c19d3-111">**헤더:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="c19d3-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="c19d3-112">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="c19d3-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="c19d3-113">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="c19d3-113">**.NET Framework Versions:** 3.5 SP1</span></span>
