---
title: "Connection.m_WriteList 필드"
ms.date: 05/01/2017
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type: apiref
api_name: System.Net.Connection.m_WriteList
api_location: System.dll
api_type: Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: guardrex
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 66454f2a165048b234dad680c6b66c6fd04bd2e3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="0745b-102">Connection.m\_WriteList 필드</span><span class="sxs-lookup"><span data-stu-id="0745b-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="0745b-103">`Connection.m_WriteList`이 <xref:System.Collections.ArrayList> 의 <xref:System.Net.HttpWebRequest> HTTP를 통해 전송 되도록 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0745b-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="0745b-104">구문</span><span class="sxs-lookup"><span data-stu-id="0745b-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="0745b-105">`Connection.m_WriteList` 필드는 전용 이며 코드에서 직접 사용할 업그레이드용은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0745b-105">The `Connection.m_WriteList` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="0745b-106">Microsoft은 프로덕션 응용 프로그램의 어떤 상황에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0745b-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0745b-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0745b-107">Requirements</span></span>

<span data-ttu-id="0745b-108">**Namespace:**<xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="0745b-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="0745b-109">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="0745b-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="0745b-110">**.NET framework 버전:** 2.0부터 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="0745b-110">**.NET Framework versions:** Available since 2.0.</span></span>
