---
title: "CoreClrDebugProcInfo 구조체"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoreClrDebugProcInfo
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 53616fb8e947d2a301dcfcb4e3870a9a9dc36ec1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="d6635-102">CoreClrDebugProcInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="d6635-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="d6635-103">원격 컴퓨터에서 실행되는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6635-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6635-104">구문</span><span class="sxs-lookup"><span data-stu-id="d6635-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="d6635-105">멤버</span><span class="sxs-lookup"><span data-stu-id="d6635-105">Members</span></span>  
  
|<span data-ttu-id="d6635-106">멤버</span><span class="sxs-lookup"><span data-stu-id="d6635-106">Member</span></span>|<span data-ttu-id="d6635-107">설명</span><span class="sxs-lookup"><span data-stu-id="d6635-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="d6635-108">OS에서 할당한 프로세스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d6635-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="d6635-109">대상 컴퓨터에서 실행되는 원격 디버깅 프록시에 의해 할당된 프로세스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d6635-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="d6635-110">이 식별자는 OS 식별자만큼 자주 재활용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6635-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="d6635-111">프로세스의 명령줄입니다.</span><span class="sxs-lookup"><span data-stu-id="d6635-111">Command-line of the process.</span></span> <span data-ttu-id="d6635-112">이 멤버는 잘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6635-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6635-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6635-113">Requirements</span></span>  
 <span data-ttu-id="d6635-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6635-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6635-115">**헤더:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="d6635-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="d6635-116">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="d6635-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="d6635-117">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d6635-117">**.NET Framework Versions:** 3.5 SP1</span></span>
