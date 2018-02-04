---
title: CoreResponseData.m_ResponseHeaders Field
ms.date: 01/29/2018
ms.prod: .net-framework
ms.technology: 
ms.topic: reference
topic_type:
- apiref
api_name:
- System.Net.CoreResponseData.m_ResponseHeaders
api_location:
- System.dll
api_type:
- Assembly
author: stevewhims
ms.author: stwhi
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: eaece5bfe9cda7d35905ecd7e1da503ec11faf9c
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="coreresponsedatamresponseheaders-field"></a>CoreResponseData.m\_ResponseHeaders Field

`CoreResponseData.m_ResponseHeaders`이 <xref:System.Net.WebHeaderCollection> 연결 된 서버 응답 헤더의 합니다.

## <a name="syntax"></a>구문
  
```csharp
public WebHeaderCollection m_ResponseHeaders
```

> [!WARNING]
> 이 API는 사용자 코드에서 직접 사용할 수는 적용 되지 않습니다. 를 대신 사용 해야는 <xref:System.Diagnostics.DiagnosticSource> 네트워킹 코드를 연결 합니다. 참조 [DiagnosticSource 사용자 가이드](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md)합니다.
> 
> Microsoft은 프로덕션 응용 프로그램의 어떤 상황에서이 클래스의 사용을 지원 하지 않습니다.

## <a name="requirements"></a>요구 사항

**Namespace:**<xref:System.Net>

**어셈블리:** 시스템 (System.dll)

**.NET framework 버전:** 2.0부터 사용 가능 합니다.
