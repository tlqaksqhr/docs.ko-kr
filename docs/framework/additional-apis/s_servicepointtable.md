---
title: ServicePointManager.s_ServicePointTable 필드
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.s_ServicePointTable
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 24459679-291c-401a-9def-e42b29466fcf
author: guardrex
ms.author: mairaw
ms.openlocfilehash: 5450a0cb3e5bd39a86365b16d372c7e573a43496
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351760"
---
# <a name="servicepointmanagersservicepointtable-field"></a>ServicePointManager.s\_ServicePointTable 필드

`ServicePointManager.s_ServicePointTable` 이 <xref:System.Collections.Hashtable> 활성 HTTP 연결의 목록이 포함 된 (<xref:System.Net.ServicePoint>s)에 <xref:System.AppDomain>합니다.

## <a name="syntax"></a>구문
  
```csharp  
private static Hashtable s_ServicePointTable
```

> [!WARNING]
> `ServicePointManager.s_ServicePointTable` 필드는 전용 이며 코드에서 직접 사용할 업그레이드용은 아닙니다.
> 
> Microsoft은 프로덕션 응용 프로그램의 어떤 상황에서이 필드의 사용을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**Namespace:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)

**.NET framework 버전:** 2.0부터 사용 가능 합니다.
