---
title: "보안 및 공용 읽기 전용 배열 필드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d86d054d3a5a4e10b8efcc3292f3a18ea37f9b87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="security-and-public-read-only-array-fields"></a>보안 및 공용 읽기 전용 배열 필드
읽기 전용 공용 배열 필드를 수정할 수 있기 때문에 경계 동작이 나 응용 프로그램의 보안을 정의 하는 관리 되는 라이브러리에서 읽기 전용 공용 배열 필드를 사용 하지 마십시오.  
  
## <a name="remarks"></a>설명  
 일부.NET framework 클래스에는 플랫폼 특정 경계 매개 변수가 포함 된 읽기 전용 공용 필드가 포함 됩니다.  예를 들어는 <xref:System.IO.Path.InvalidPathChars> 필드는 파일 경로 문자열에서 허용 되지 않는 문자를 설명 하는 배열입니다.  .NET Framework 전반에 걸쳐 많은 것과 유사한 필드가 있습니다.  
  
 와 같은 공용 읽기 전용 필드의 값 <xref:System.IO.Path.InvalidPathChars> 코드 또는 사용자 코드의 응용 프로그램 도메인을 공유 하 여 수정할 수 있습니다.  응용 프로그램의 경계 동작을 정의 하려면 다음과 같이 읽기 전용 공용 배열 필드를 사용 하지 마십시오.  이렇게 하면 악의적인 코드는 경계 정의 변경 하 고 코드를 사용 하 여 예기치 않은 방법으로 수 있습니다.  
  
 2.0 및.NET Framework의 나중 버전에서 공용 배열 필드를 사용 하는 대신 새 배열을 반환 하는 메서드를 사용 해야 합니다.  예를 들어, 사용 하는 대신는 <xref:System.IO.Path.InvalidPathChars> 필드를 사용할지는 <xref:System.IO.Path.GetInvalidPathChars%2A> 메서드.  
  
 참고가.NET Framework 형식 경계 유형을 내부적으로 정의 하는 공용 필드를 사용 하지 마십시오.  대신,.NET Framework는 별도 전용 필드를 사용 합니다.  이러한 공용 필드의 값을 변경 하는 경우에.NET Framework 형식의 동작을 변경 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)
