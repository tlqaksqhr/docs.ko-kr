---
title: 예외 및 성능
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- tester-doer pattern
- TryParse pattern
- exceptions, throwing
- exceptions, performance
- throwing exceptions, performance
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfffc2a1c0f607541194a7f51717d5bf8a8537f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-and-performance"></a>예외 및 성능
예외와 관련 된 일반적인 문제 하나는 지속적으로 실패 하는 코드에 대 한 예외를 사용 하면 성능을 구현 됩니다 허용입니다. 이 유효한 중요 합니다. 예외를 throw 하는 멤버 성능이 현저히 저하 될 수 있습니다. 그러나, 오류 코드를 사용 하지 않도록 설정 하는 예외 지침을 따르면 엄격 하 게 하는 동안 좋은 성능을 얻을 수는 있습니다. 이 섹션에 설명 된 두 개의 패턴에는이 작업을 수행 하는 방법을 제안 합니다.  
  
 **X 하지 않으면** 있는지 예외 영향을 줄 수 성능 저하 문제 때문에 오류 코드를 사용 합니다.  
  
 성능을 향상 시키기 위해 Tester-doer 패턴 나 다음 두 섹션에서 설명 하는 Try 구문 분석 패턴을 사용 하는 것이 같습니다.  
  
## <a name="tester-doer-pattern"></a>Tester-doer 패턴  
 경우에 따라 성능 예외 throw 멤버의 멤버 두 개로 나누어 향상 될 수 있습니다. 에 <xref:System.Collections.Generic.ICollection%601.Add%2A> 의 메서드는 <xref:System.Collections.Generic.ICollection%601> 인터페이스입니다.  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 메서드가 `Add` 컬렉션이 읽기 전용인 경우 throw 합니다. 이 자주 실패 하 고 메서드 호출 필요한 시나리오에서 성능 문제를 수 있습니다. 문제를 완화 하는 방법 중 하나는 컬렉션 값을 추가 하기 전에 쓰기 가능 인지를 테스트 하는 것입니다.  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 속성은 예에서 사용 하는 조건을 테스트 하는 데 사용 하는 멤버 `IsReadOnly`은 테스터 라고 합니다. 잠재적으로 발생 작업을 수행 하는 데 사용 되는 멤버는 `Add` 예에서 메서드 doer 부분으로 참조 됩니다.  
  
 **✓ 고려** Tester-doer 패턴 예외를 throw 할 수 있는 멤버에 대 한 공통 성능 문제를 방지 하는 시나리오와 관련 된 예외입니다.  
  
## <a name="try-parse-pattern"></a>시도 구문 분석 패턴  
 성능이 매우 중요 한 Api에 대 한 이전 섹션에서 설명한 Tester-doer 패턴 보다 훨씬 빠른는 패턴을 사용 해야 합니다. 멤버 이름에 멤버 의미 체계의 일부 경우 잘 정의 된 테스트를 조정 하기 위한 패턴을 호출 합니다. 예를 들어 <xref:System.DateTime> 정의 <xref:System.DateTime.Parse%2A> 메서드는 실패 하는 문자열을 구문 분석 하는 경우 예외를 throw 합니다. 또한 해당 정의 <xref:System.DateTime.TryParse%2A> , 구문 분석을 시도 하는 하지만 메서드 구문 분석 실패 하 고 사용 하 여 성공적으로 구문 분석의 결과 반환 하는 경우는 `out` 매개 변수입니다.  
  
```  
public struct DateTime {  
    public static DateTime Parse(string dateTime){   
        ...   
    }  
    public static bool TryParse(string dateTime, out DateTime result){  
        ...  
    }  
}  
```  
  
 이 패턴을 사용할 경우에 엄격한 측면에서 시도 기능을 정의 해야 합니다. 멤버 잘 정의 된 try 이외의 어떤 이유로 든 실패할 경우 멤버에 해당 하는 예외가 throw 여전히 해야 합니다.  
  
 **✓ 고려** Try 구문 분석 패턴 예외를 throw 할 수 있는 멤버에 대 한 공통 성능 문제를 방지 하는 시나리오와 관련 된 예외입니다.  
  
 **✓ 않습니다** 이 패턴을 구현 하는 방법에 대 한 접두사 "Try" 및 Boolean 반환 형식을 사용 합니다.  
  
 **✓ 않습니다** Try 구문 분석 패턴을 사용 하 여 각 멤버에 대 한 예외 throw 멤버를 제공 합니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [예외 디자인 지침](../../../docs/standard/design-guidelines/exceptions.md)
