---
title: Connection.m_WriteList 필드
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection.m_WriteList
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 235503c1-1d01-4f59-895f-ae2cf15b3345
author: guardrex
ms.author: mairaw
ms.openlocfilehash: d145f6fd21989ada49a581ebf2694dcd56d94351
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743162"
---
# <a name="connectionmwritelist-field"></a><span data-ttu-id="58597-102">Connection.m\_WriteList 필드</span><span class="sxs-lookup"><span data-stu-id="58597-102">Connection.m\_WriteList Field</span></span>

<span data-ttu-id="58597-103">`Connection.m_WriteList` 이 <xref:System.Collections.ArrayList> 의 <xref:System.Net.HttpWebRequest> HTTP를 통해 전송 되도록 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="58597-103">`Connection.m_WriteList` is an <xref:System.Collections.ArrayList> of <xref:System.Net.HttpWebRequest> objects that are queued up to be sent over HTTP.</span></span>

## <a name="syntax"></a><span data-ttu-id="58597-104">구문</span><span class="sxs-lookup"><span data-stu-id="58597-104">Syntax</span></span>
  
```csharp  
private ArrayList m_WriteList
```

> [!WARNING]
> <span data-ttu-id="58597-105">`Connection.m_WriteList` 필드는 전용 이며 코드에서 직접 사용할 업그레이드용은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="58597-105">The `Connection.m_WriteList` field is private and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="58597-106">Microsoft은 프로덕션 응용 프로그램의 어떤 상황에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58597-106">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="58597-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58597-107">Requirements</span></span>

<span data-ttu-id="58597-108">**Namespace:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="58597-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="58597-109">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="58597-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="58597-110">**.NET framework 버전:** 2.0부터 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="58597-110">**.NET Framework versions:** Available since 2.0.</span></span>
