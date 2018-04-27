---
title: 생성자 디자인
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d208511bd04d5daf9930ecf6cf53e7708ca4da3f
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="constructor-design"></a>생성자 디자인
생성자의 두 종류가: 생성자 및 인스턴스 생성자를 입력 합니다.  
  
 형식 생성자는 정적이 고 해당 형식이 사용 하기 전에 CLR에서 실행 됩니다. 인스턴스 생성자에는 형식의 인스턴스를 만들 때 실행 합니다.  
  
 형식 생성자 매개 변수를 사용할 수 없습니다. 인스턴스 생성자는 다음 작업을 할 수 있습니다. 인스턴스 생성자 매개 변수를 사용 하지 않는 기본 생성자 라고도 합니다.  
  
 생성자는 형식의 인스턴스를 만들 수는 가장 일반적인 방법입니다. 대부분의 개발자가 검색 하 고 (예: 팩터리 메서드) 인스턴스를 만드는 다른 방법을 고려 하기 전에 생성자를 사용 하려고 합니다.  
  
 **✓ 고려** 단순, 이상적으로 기본적으로 생성자를 제공 합니다.  
  
 간단한 생성자는 매우 적은 수의 매개 변수를 가지 며 모든 매개 변수는 기본 형식 또는 열거형 이러한 간단한 생성자 프레임 워크의 유용성을 늘립니다.  
  
 **✓ 고려** 원하는 작업의 의미 체계의 새 인스턴스를 생성에 직접 매핑되지 않는 경우 또는 비 자연 느낌 생성자 설계 지침을 따르는 경우 생성자를 대신 정적 팩터리 메서드를 사용 합니다.  
  
 **✓ 않습니다** 가기로 생성자 매개 변수를 사용 하 여 기본 속성을 설정 합니다.  
  
 의미 체계 사이에서 차이가 없어야 없어야 빈 생성자 일부 속성 집합을 통해 다음을 사용 하 고 생성자를 사용 하 여 여러 인수를 사용 합니다.  
  
 **✓ 않습니다** 생성자 매개 변수는 단순히 속성을 설정 하는 데 사용 되는 경우 생성자 매개 변수 및 속성에 대 한 동일한 이름을 사용 합니다.  
  
 이러한 매개 변수 및 속성 간의 유일한 차이점 대/소문자 구분 합니다.  
  
 **✓ 않습니다** 생성자에서 최소한의 작업만 있습니다.  
  
 생성자 수행 해야 캡처 이외의 얼마나 많은 작업이 생성자 매개 변수. 필요할 때까지 다른 처리 비용을 지연 해야 합니다.  
  
 **✓ 않습니다** 해당 되는 경우에 인스턴스 생성자에서 예외를 throw 합니다.  
  
 **✓ 않습니다** 이러한 생성자가 필요한 경우 클래스, public 기본 생성자를 명시적으로 선언 합니다.  
  
 형식에서 생성자를 명시적으로 선언 하지 않습니다, 여러 언어 (예: C#) 공용 기본 생성자를 자동으로 추가 됩니다. (추상 클래스는 protected 생성자를 가져옵니다.)  
  
 컴파일러가 기본 생성자를 추가 하지 클래스에 매개 변수화 된 생성자를 추가 합니다. 실수로 인 한 주요 변경 내용 종종 그러면합니다.  
  
 **하지 말고 X** 구조체에 기본 생성자를 명시적으로 정의 합니다.  
  
 따라서 배열 생성 더 빨리 없기 때문에 기본 생성자를 정의 하지 않은 경우이를 배열에 있는 모든 슬롯에서 실행할 수 있습니다. C#을 포함 하 여 많은 컴파일러에서는이 매개 변수가 없는 생성자가 있는 경우에 구조체를 허용 하지 않음 note 합니다.  
  
 **하지 말고 X** 개체의 생성자 내에서 가상 멤버를 호출 합니다.  
  
 가상 멤버를 호출 하면 가장 많이 파생 된 재정의를 호출할 수는 가장 많이 파생 된 형식의 생성자가 완전히 아직 실행 되지 하는 경우에 합니다.  
  
### <a name="type-constructor-guidelines"></a>형식 생성자 지침  
 **✓ 않습니다** 정적 생성자를 private입니다.  
  
 형식을 초기화 하는 클래스 생성자를 호출 또한 정적 생성자는 사용 됩니다. CLR 형식의 첫 번째 인스턴스가 만들어지거나 해당 형식에 정적 멤버 호출 되기 전에 static 생성자를 호출 합니다. 사용자에 정적 생성자를 호출 하는 경우 제어할 수 없습니다. 정적 생성자가 private이 아니면 CLR 이외의 코드에서 호출할 수 있습니다. 생성자에서 수행 하는 작업에 따라 이렇게 예기치 않은 동작이 발생할 수 있습니다. C# 컴파일러를 전용 정적 생성자를 강제로 수행 합니다.  
  
 **X 하지 않으면** 정적 생성자에서 예외를 throw 합니다.  
  
 형식 생성자에서 예외가 발생 하는 경우 형식에에서 없는 경우 사용할 수 있는 현재 응용 프로그램 도메인  
  
 **✓ 고려** 런타임 형식에서 명시적으로 정의 된 정적 생성자를 갖지 않는의 성능을 최적화할 수 있기 때문에 정적 생성자를 사용 하 여 명시적으로 보다는 정적 필드 인라인을 초기화 합니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
