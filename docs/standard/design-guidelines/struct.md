---
title: 구조체 디자인
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2621aa96cf89b453d5faec3357d0890ca36251d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572738"
---
# <a name="struct-design"></a>구조체 디자인
범용 값 형식이 가장 자주 C# 키워드는 구조체 라고 합니다. 이 섹션에서는 일반 구조체 디자인에 대 한 지침을 제공 합니다.  
  
 **X DO NOT** 구조체에 대 한 기본 생성자를 제공 합니다.  
  
 이 지침에 따라 배열을 구조체를 배열의 각 항목에는 생성자를 실행할 필요 없이 만들 수 있습니다. C#에서는 기본 생성자가 있는 경우에 구조체를 확인 합니다.  
  
 **X DO NOT** 변경할 수 있는 값 형식을 정의 합니다.  
  
 변경 가능한 값 형식에 몇 가지 문제가 있습니다. 예를 들어, 속성 getter 값 형식을 반환 하는 경우 호출자에 게 복사본을 받습니다. 복사본을 암시적으로 생성 되므로 개발자는 복사 및 원래 값이 아니라 변경할는 인식 아닐 수 있습니다. 또한, 일부 언어 (특히에서 동적 언어)는 문제 때문에 변경할 수 있는 값 형식을 사용 하 여 지역 변수를 포함 하 여 역참조 시, 하면 복사 만들 수 있습니다.  
  
 **✓ DO** 0으로 설정 되어 있는 모든 인스턴스 데이터는 상태, false 또는 적절 하 게 null 올바른지 확인 합니다.  
  
 이렇게 하면 의도치 않게 잘못 된 인스턴스 만들기를 구조체의 배열을 만들 때 않습니다.  
  
 **✓ DO** 구현 <xref:System.IEquatable%601> 값 형식에 있습니다.  
  
 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 값 형식에서 메서드를 boxing을 사용 하면 고 리플렉션을 사용 하기 때문에 기본 구현 효율적이 지 않습니다. <xref:System.IEquatable%601.Equals%2A> 성능을 향상을 가질 수 있습니다 및 boxing이 발생 하지 것입니다 있도록 구현할 수 있습니다.  
  
 **X DO NOT** 명시적으로 확장 <xref:System.ValueType>합니다. 실제로 대부분의 언어가를 방지 합니다.  
  
 일반적으로 구조체 매우 유용할 수 있지만 자주 boxed 하지 하는 작은를 변경할 수 없는 단일 값만 사용 해야 합니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [형식 디자인 지침](../../../docs/standard/design-guidelines/type.md)  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [클래스와 구조체 간의 선택](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
