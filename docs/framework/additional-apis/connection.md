---
title: "Connection 클래스"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.Connection
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 6f0b8902-f31c-4ab9-a8c9-de43228995ec
author: guardrex
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 02303a584aca738718d3e69a0071b40690fa055a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="connection-class"></a><span data-ttu-id="fdbec-102">Connection 클래스</span><span class="sxs-lookup"><span data-stu-id="fdbec-102">Connection Class</span></span>

<span data-ttu-id="fdbec-103">`Connection` 클래스 구문 분석 하 여 서버 응답, 큐 요청과 파이프라인 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdbec-103">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="fdbec-104">구문</span><span class="sxs-lookup"><span data-stu-id="fdbec-104">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="fdbec-105">`Connection` 클래스는 내부 전용 이며 코드에서 직접 사용할 업그레이드용은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fdbec-105">The `Connection` class is internal and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="fdbec-106">Microsoft은 프로덕션 응용 프로그램의 어떤 상황에서이 클래스의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fdbec-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="fdbec-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fdbec-107">Requirements</span></span>

<span data-ttu-id="fdbec-108">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="fdbec-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="fdbec-109">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="fdbec-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="fdbec-110">**.NET framework 버전:** 2.0부터 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="fdbec-110">**.NET Framework versions:** Available since 2.0.</span></span>
