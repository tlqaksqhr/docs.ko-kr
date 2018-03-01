---
title: "ConnectionGroup 클래스"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 25c08217-fdeb-44b9-9cd6-1b4955d6e602
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2740136d4ef7377357baa1bc30a7f1c05072c73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="connectiongroup-class"></a><span data-ttu-id="96916-102">ConnectionGroup 클래스</span><span class="sxs-lookup"><span data-stu-id="96916-102">ConnectionGroup Class</span></span>

<span data-ttu-id="96916-103">`ConnectionGroup` 클래스 내에서 연결 목록을 그룹화는 <xref:System.Net.ServicePoint> 컨텍스트는 네트워크 리소스 (예: 프록시 및 별도 클라이언트)에 대 한 컨텍스트를 유지 관리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96916-103">The `ConnectionGroup` class groups a list of connections within the <xref:System.Net.ServicePoint> context and is used to maintain context for network resources (for example, proxies and separate clients).</span></span>

## <a name="syntax"></a><span data-ttu-id="96916-104">구문</span><span class="sxs-lookup"><span data-stu-id="96916-104">Syntax</span></span>
  
```csharp  
internal class ConnectionGroup
```

> [!WARNING]
> <span data-ttu-id="96916-105">`ConnectionGroup` 클래스는 내부 전용 이며 코드에서 직접 사용할 업그레이드용은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="96916-105">The `ConnectionGroup` class is internal and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="96916-106">Microsoft은 프로덕션 응용 프로그램의 어떤 상황에서이 클래스의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96916-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="96916-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="96916-107">Requirements</span></span>

<span data-ttu-id="96916-108">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="96916-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="96916-109">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="96916-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="96916-110">**.NET framework 버전:** 2.0부터 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="96916-110">**.NET Framework versions:** Available since 2.0.</span></span>
