---
title: "예외 및 성능 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "tester-doer 패턴"
  - "TryParse 패턴"
  - "예외를 throw"
  - "예외, 성능"
  - "성능 예외를 throw합니다."
ms.assetid: 3ad6aad9-08e6-4232-b336-0e301f2493e6
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 예외 및 성능
예외와 관련 된 하나의 일반적인 문제는 지속적으로 실패 하는 코드에 대 한 예외를 사용할 경우는 구현의 성능이 됩니다 허용입니다. 맞는 말입니다. 예외를 throw 하는 멤버 성능이 배나 저하 될 수 있습니다. 그러나 오류 코드를 사용 하지 않도록 설정 하는 예외 지침을 준수할 엄격 하 게 하는 동안 적절 한 성능을 달성 하는 것이 같습니다. 이 섹션에서 설명 하는 두 가지 패턴에는이 작업을 수행 하는 방법을 제안 합니다.  
  
 **X 하지 않으려면** 는 예외 영향을 줄 수 성능 저하 문제 때문에 오류 코드를 사용 합니다.  
  
 성능 향상을 위해 Tester\-doer 패턴 또는 다음 두 섹션에 설명 된 Try 구문 분석 패턴을 사용 하는 것이 같습니다.  
  
## Tester\-doer 패턴  
 경우에 따라 성능 예외를 throw 할 멤버의 멤버를 두 개로 분할 하 여 개선할 수 있습니다. 에 대해 살펴보겠습니다는 <xref:System.Collections.Generic.ICollection%601.Add%2A> 의 메서드는 <xref:System.Collections.Generic.ICollection%601> 인터페이스입니다.  
  
```  
ICollection<int> numbers = ...   
numbers.Add(1);  
```  
  
 메서드가 `Add` 컬렉션이 읽기 전용인 경우 throw 됩니다. 이 있는 메서드를 호출 해야 하는 자주 실패 하는 시나리오에서 성능 문제를 수 있습니다. 문제를 완화 하는 방법 중 하나는 컬렉션 값을 추가 하려고 하기 전에 쓰기 가능 인지를 테스트 하는 것입니다.  
  
```  
ICollection<int> numbers = ...   
...  
if(!numbers.IsReadOnly){  
    numbers.Add(1);  
}  
```  
  
 속성은 예에서 사용 하는 조건을 테스트 하는 데 사용 하는 멤버 `IsReadOnly`, 테스터 라고 합니다. 잠재적으로 발생 작업을 수행 하는 데 사용 되는 멤버는 `Add` 예에서 메서드 doer 부분 이라고 합니다.  
  
 **✓ 고려** Tester\-doer 패턴 예외를 throw 할 수 있는 멤버에 대 한 공통 성능 문제를 방지 하는 시나리오와 관련 된 예외입니다.  
  
## Try 구문 분석 패턴  
 성능이 매우 중요 한 Api에 대 한 이전 섹션에 설명 된 Tester\-doer 패턴 보다는 훨씬 빠른 패턴을 사용 해야 합니다. 패턴 멤버 이름에 일부 멤버 의미 체계의 경우는 잘 정의 된 테스트를 조정 하기 위해 호출 합니다. 예를 들어 <xref:System.DateTime> 정의 <xref:System.DateTime.Parse%2A> 실패 하는 문자열을 구문 분석 하는 경우 예외를 throw 하는 메서드입니다. 또한 해당 정의 <xref:System.DateTime.TryParse%2A> 구문 분석 하려고 하는 하지만 메서드 구문 분석 실패 하 고 사용 하 여 성공적으로 구문 분석의 결과 반환 하는 경우는 `out` 매개 변수입니다.  
  
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
  
 이 패턴을 사용할 때에 엄격한 용어로 시도 기능을 정의 하는 것이 중요 합니다. 잘 정의 된 try 이외의 어떤 이유로 든 실패 하면 멤버 멤버는 해당 예외를 아직 throw 해야 합니다.  
  
 **✓ 고려** Try 구문 분석 패턴 예외를 throw 할 수 있는 멤버에 대 한 공통 성능 문제를 방지 하는 시나리오와 관련 된 예외입니다.  
  
 **✓ 수행** 이 패턴을 구현 하는 방법에 대 한 "Try" 및 Boolean 반환 형식을 접두사를 사용 합니다.  
  
 **✓ 수행** Try 구문 분석 패턴을 사용 하 여 각 멤버에 대 한 예외를 throw 할 멤버를 제공 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [예외에 대 한 디자인 지침](../../../docs/standard/design-guidelines/exceptions.md)