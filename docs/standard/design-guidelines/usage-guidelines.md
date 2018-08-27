---
title: 사용 지침
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bd54a2325c9721ad17943ba663e7ec0c300632e
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925078"
---
# <a name="usage-guidelines"></a>사용 지침

이 섹션에서는 일반적인 형식을 사용 하 여 공개적으로 액세스할 수 있는 api에 대 한 지침을 포함 합니다. 기본 제공 프레임 워크 형식 (예: serialization 특성) 및 일반적인 연산자 오버 로드를 직접 사용 하 여 다룹니다.
  
<xref:System.IDisposable?displayProperty=nameWithType> 인터페이스는이 섹션에서는 다루지 않습니다 하지만 부분은 합니다 [Dispose 패턴](../../../docs/standard/design-guidelines/dispose-pattern.md) 섹션.

> [!NOTE]
> 지침 및 다른 일반적인 방법에 대 한에 대 한 추가 정보에 대 한 기본 제공.NET Framework 형식으로 다음 참조 항목을 참조 하세요. <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.

## <a name="in-this-section"></a>단원 내용

[배열](arrays.md)  
[특성](attributes.md)  
[컬렉션](guidelines-for-collections.md)  
[serialization](serialization.md)  
[System.Xml 사용법](system-xml-usage.md)  
[같음 연산자](equality-operators.md)  

*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*

*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*
  
## <a name="see-also"></a>참고자료

[프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
