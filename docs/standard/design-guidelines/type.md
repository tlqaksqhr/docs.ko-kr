---
title: 형식 디자인 지침
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af7511f4159fdbfe2d3f972dc927e9ee11fd586f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572891"
---
# <a name="type-design-guidelines"></a>형식 디자인 지침
CLR 관점에서는 두 가지 범주의 형식-참조 형식과 값 형식-하지만 프레임 워크 디자인에 대 한 토론을 목적으로 각각의 특정 디자인 규칙 자체에 더 많은 논리 그룹으로 형식 나눕니다.  
  
 클래스는 참조 형식의 일반적인 경우입니다. 대부분의 프레임 워크에 있는 형식의 대량을 구성 합니다. 클래스는 다양 한 개체 지향 기능을 지원 하 고 일반의 적용 가능성 사람들이 미납 합니다. 기본 클래스와 추상 클래스는 확장성와 관련 된 특별 한 논리 그룹입니다.  
  
 인터페이스는 참조 형식과 값 형식으로 구현할 수 있는 형식입니다. 따라서 참조 형식과 값 형식의 다형적 계층의 루트도 사용할 수 있습니다. 또한 기본적으로 CLR에서 지원 되지 않는 여러 상속을 시뮬레이트하려 인터페이스를 사용할 수 있습니다.  
  
 구조체는 값 형식의 일반적인 경우는 및 언어 기본 형식에서와 유사한 간단한 형식에 대 한 예약 되어야 합니다.  
  
 열거형은 짧은 집합 주와 콘솔 색 등의 일 등의 값을 정의 하는 데 사용 되는 값 형식의 특별 한 경우입니다.  
  
 정적 클래스는 형식 정적 멤버에 대 한 컨테이너 되도록 만들어졌습니다. 일반적으로 다른 작업에 대 한 바로 가기를 제공에 사용 됩니다.  
  
 대리자, 예외, 특성, 배열 및 컬렉션은 특정 용도 위한 참조 형식의 모든 특별 한 경우 및 설계 및 사용에 대 한 지침이이 가이드에서 다른 위치에서 설명 합니다.  
  
 **✓ 않습니다** 각 형식이 관련 되지 않은 기능의 임의 컬렉션 뿐 아니라 관련된 멤버의 잘 정의 된 집합 지 확인 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [클래스와 구조체 간의 선택](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [추상 클래스 디자인](../../../docs/standard/design-guidelines/abstract-class.md)  
 [정적 클래스 디자인](../../../docs/standard/design-guidelines/static-class.md)  
 [인터페이스 디자인](../../../docs/standard/design-guidelines/interface.md)  
 [구조체 디자인](../../../docs/standard/design-guidelines/struct.md)  
 [열거형 디자인](../../../docs/standard/design-guidelines/enum.md)  
 [중첩 형식](../../../docs/standard/design-guidelines/nested-types.md)  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
