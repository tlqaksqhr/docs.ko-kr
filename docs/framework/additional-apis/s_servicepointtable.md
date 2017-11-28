---
title: "ServicePointManager.s_ServicePointTable 필드"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type: apiref
api_name: System.Net.ServicePointManager.s_ServicePointTable
api_location: System.dll
api_type: Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2f12a8ba4d2b84e5b5d73d26199adf687a95a2df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="servicepointmanagersservicepointtable-field"></a><span data-ttu-id="b7b43-102">ServicePointManager.s\_ServicePointTable 필드</span><span class="sxs-lookup"><span data-stu-id="b7b43-102">ServicePointManager.s\_ServicePointTable Field</span></span>

<span data-ttu-id="b7b43-103">`ServicePointManager.s_ServicePointTable`이 <xref:System.Collections.Hashtable> 활성 HTTP 연결의 목록이 포함 된 (<xref:System.Net.ServicePoint>s)에 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-103">`ServicePointManager.s_ServicePointTable` is a <xref:System.Collections.Hashtable> that contains the list of active HTTP connections (<xref:System.Net.ServicePoint>s) in the <xref:System.AppDomain>.</span></span>

## <a name="syntax"></a><span data-ttu-id="b7b43-104">구문</span><span class="sxs-lookup"><span data-stu-id="b7b43-104">Syntax</span></span>
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> <span data-ttu-id="b7b43-105">`ServicePointManager.s_ServicePointTable` 필드는 전용 이며 코드에서 직접 사용할 업그레이드용은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-105">The `ServicePointManager.s_ServicePointTable` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="b7b43-106">Microsoft은 프로덕션 응용 프로그램의 어떤 상황에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b7b43-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7b43-107">Requirements</span></span>

<span data-ttu-id="b7b43-108">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="b7b43-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="b7b43-109">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="b7b43-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="b7b43-110">**.NET framework 버전:** 2.0부터 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7b43-110">**.NET Framework versions:** Available since 2.0.</span></span>
