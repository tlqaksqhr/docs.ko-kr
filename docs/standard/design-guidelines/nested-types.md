---
title: 중첩 형식
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c0eca851746899654636d36dce679acffc07ef0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="nested-types"></a>중첩 형식
중첩된 형식은 바깥쪽 형식의 호출 하는 다른 형식의 범위 내에 정의 된 하는 형식이입니다. 중첩된 형식은 바깥쪽 형식의 모든 멤버 권한이 있습니다. 예를 들어 바깥쪽 형식의 모든 상위 항목에 정의 된 필드를 보호 및 바깥쪽 형식에 정의 된 전용 필드에 액세스를 권한이 있습니다.  
  
 일반적으로 중첩 된 형식은 제한적으로 사용 해야 합니다. 여기에는 여러 가지 이유가 있습니다. 일부 개발자가 완전히 개념에 익숙하지 않습니다. 이러한 개발자 중첩 형식의 변수 선언 구문 사용 하 여 문제가 예를 들어 될 수 있습니다. 중첩된 형식은 바깥쪽 형식을 매우 밀접 하 게 결합 하 고 따라서 범용 형식에 적합 하지 않습니다.  
  
 중첩된 형식은 자신의 바깥쪽 유형의 구현 세부 사항을 모델링에 적합 합니다. 최종 사용자는 중첩 형식의 변수를 선언 하 거의 있어야 하 고 거의 중첩된 형식을 명시적으로 인스턴스화할 수 있어야 합니다. 예를 들어 컬렉션의 열거자에는 해당 컬렉션의 중첩 된 형식일 수 있습니다. 열거자는 바깥쪽 형식에 의해 인스턴스화될 일반적으로 있으며 하므로 대부분의 언어 지원 foreach 문을, 열거자 변수 거의 최종 사용자가 선언 합니다.  
  
 **✓ 않습니다** 중첩된 형식 및 해당 외부 형식 간의 관계는 멤버 액세스 가능성 의미 체계는 바람직한 되도록 하는 경우 중첩 된 형식을 사용 합니다.  
  
 **X 하지 않으면** 논리적 그룹으로 사용 하 여 공용 중첩된 형식은 생성;이 대 한 네임 스페이스를 사용 합니다.  
  
 **하지 말고 X** 중첩된 형식은 공개적으로 노출 됩니다. 이 유일한 예외는 중첩 형식의 변수를 서브클래싱 또는 기타 고급 사용자 지정 시나리오 예: 드문 시나리오 에서만에서 선언 해야 하는 경우.  
  
 **X 하지 않으면** 형식이 포함 하는 형식 외부에서 참조 될 가능성이 높은 경우 중첩 된 형식을 사용 합니다.  
  
 예를 들어, 클래스에 정의 된 메서드에 전달 되는 enum 클래스에서 중첩 된 형식으로 정의 되어야 합니다.  
  
 **X 하지 않으면** 클라이언트 코드에서 인스턴스화 대상으로 해야 하는 경우 중첩 된 형식을 사용 합니다.  형식에 public 생성자를 중첩 하지 않을 안 됩니다.  
  
 이 매우를 나타내는 형식에는 자체적으로 프레임 워크에 적합 한 형식을 인스턴스화할 수, 하는 경우 (있습니다 수 만들, 작업, 및 외부 형식을 사용할 필요 없이 삭제), 따라서 중첩 해야 합니다. 내부 형식 관계 없는 외부 형식 외부에서 광범위 하 게 재사용 되지 않아야 외부 형식에 어떠한 합니다.  
  
 **X 하지 않으면** 인터페이스의 구성원으로 중첩 된 형식을 정의 합니다. 대부분의 언어에서는 이러한 구문을 지원 하지 않습니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [형식 디자인 지침](../../../docs/standard/design-guidelines/type.md)  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
