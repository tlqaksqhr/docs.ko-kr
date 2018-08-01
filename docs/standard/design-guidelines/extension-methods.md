---
title: 확장명 메서드
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15d36cc2d3073c9f695de81407ecabcd5e3bba30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574519"
---
# <a name="extension-methods"></a>확장명 메서드
확장 메서드는 정적 메서드를 인스턴스 메서드 호출 구문을 사용 하 여 호출할 수 있는 언어 기능. 이러한 메서드는 방법은에 대해 작동 하는 인스턴스를 나타내는 하나 이상의 매개 변수를 사용 해야 합니다.  
  
 이러한 확장 메서드를 정의 하는 클래스는 "스폰서" 클래스 라고 하 고 정적으로 선언 되어야 합니다. 확장 메서드를 사용 하려면 스폰서 클래스를 정의 하는 네임 스페이스 하나 가져와야 합니다.  
  
 **X AVOID** frivolously 소유 하지 않은 형식에서 특히 확장 메서드를 정의 합니다.  
  
 형식의 소스 코드를가지고 않으면 일반 인스턴스 메서드를 대신 사용 하는 것이 좋습니다. 소유 하지 않은 메서드를 추가 하려는 경우 매우 주의 해야 합니다. 자유롭게 사용 하 여 확장 메서드는 이러한 메서드를 포함 하도록 설계 되지 않은 형식의 Api 복잡 하 게 만들지 가능성이 있습니다.  
  
 **✓ CONSIDER** 확장 메서드를 사용 하 여 다음과 같은 시나리오 중 하나:  
  
-   도우미를 제공 하기 핵심 인터페이스에 대해 기능 이라고 하는 경우 모든 구현 된 인터페이스의 관련 기능을 작성할 수 있습니다. 즉, 구체적 구현을 그렇지 않으면 인터페이스에 할당할 수 없습니다. 예를 들어는 `LINQ to Objects` 연산자는 모든 확장 메서드로 구현 됩니다 <xref:System.Collections.Generic.IEnumerable%601> 형식입니다. 따라서 `IEnumerable<>` 구현이 자동으로 LINQ 사용 되었습니다.  
  
-   일부 형식에 대 한 종속성 하지만 이러한 종속성 인스턴스 메서드인 것 소개 하는 경우 종속성 관리 규칙 작동 하지 않으므로 합니다. 예를 들어 종속성 <xref:System.String> 를 <xref:System.Uri?displayProperty=nameWithType> 바람직합니다 하지 않을 하므로 `String.ToUri()` 반환 하는 인스턴스 메서드 `System.Uri` 종속성 관리 측면에서 잘못 된 디자인 합니다. 정적 확장 메서드 `Uri.ToUri(this string str)` 반환 `System.Uri` 것이 더 나은 디자인 합니다.  
  
 **X AVOID** 에서 확장 메서드를 정의 <xref:System.Object?displayProperty=nameWithType>합니다.  
  
 VB 사용자 확장 메서드 구문을 사용 하 여 개체 참조에서 이러한 메서드를 호출할 수 없습니다. VB VB에서 바인딩된 개체를 가져오면 되도록 런타임에 대 한 모든 메서드 호출으로 대 한 참조를 선언 하기 때문에 이러한 메서드 호출을 지원 하지 않습니다 (실제 멤버는 런타임에 결정 됨), 확장 방법에 대 한 바인딩을 컴파일 시간 (초기에 결정 되는 동안 바인딩된).  
  
 지침의 동일한 바인딩 동작이 존재 하는 다른 언어에 적용 되는지 또는 확장 메서드가 지원 되지 않습니다.  
  
 **X DO NOT** 종속성 관리 또는 인터페이스에 메서드 추가 하지 않은 확장된 유형으로 동일한 네임 스페이스에 확장 메서드를 배치 합니다.  
  
 **X AVOID** 다른 네임 스페이스에 상주 하는 경우에 동일한 서명으로 두 개 이상의 확장 메서드를 정의 합니다.  
  
 **✓ CONSIDER** 형식이 인터페이스 및 확장 메서드는 대부분 또는 모든 경우에 사용 하려는 경우 확장된 유형으로 동일한 네임 스페이스의 확장 메서드를 정의 합니다.  
  
 **X DO NOT** 다른 기능과 함께 일반적으로 관련 된 네임 스페이스에는 기능을 구현 하는 확장 메서드를 정의 합니다. 대신에 속해 기능과 관련 된 네임 스페이스에서 정의 합니다.  
  
 **X AVOID** 확장 메서드 (예: "확장")에 네임 스페이스의 일반 이름을 지정 합니다. 설명이 포함 된 이름을 사용 하 여 (예: "라우팅") 대신.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
