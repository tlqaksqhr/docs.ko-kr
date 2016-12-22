---
title: "What&#39;s New for Visual C# | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: 9f18dc26-27fa-4603-a639-b573f07a117b
caps.latest.revision: 39
caps.handback.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# What&#39;s New for Visual C# #
[!INCLUDE[vs2017banner](../../csharp/includes/vs2017banner.md)]

이 페이지에는 각 C\# 버전의 주요 기능 이름과 최신 C\# 버전의 새로운 기능 및 향상된 기능에 대한 설명이 정리되어 있습니다.  
  
## 이전 버전  
 C\# 1, Visual Studio .NET 2002  
 첫 번째 릴리스  
  
 C\# 1.1, Visual Studio .NET 2003  
 `#line` pragma 및 xml 문서 주석  
  
 C\# 2, Visual Studio .NET 2005  
 무명 메서드, 제네릭, nullable 형식, 반복기\/yield, `static` 클래스, 대리자의 공변성\(Covariance\)\/반공변성\(Contravariance\)  
  
 C\# 3, Visual Studio .NET 2008  
 개체 및 컬렉션 이니셜라이저, 람다 식, 확장 메서드, 익명 형식, 자동 속성, LINQ\(Language Integrated Query\), 익명 형식, 로컬 `var` 형식 유추, LINQ  
  
 C\# 4, Visual Studio .NET 2010  
 `Dynamic`, 명명된 인수, 선택적 매개 변수, 제네릭 공변성\(Covariance\)\/반공변성\(Contravariance\)  
  
 C\# 5, Visual Studio .NET 2012  
 `Async` \/ `await`, 호출자 정보 특성  
  
 Visual Studio .NET 2013  
 버그 수정, 성능 향상 및 .NET 컴파일러 플랫폼\("Roslyn"\)의 기술 미리 보기  
  
 C\# 6, Visual Studio .NET 2015  
 현재 버전, 아래 참조  
  
## 현재 버전  
 [nameof](../../csharp/language-reference/keywords/nameof.md)  
 문자열을 하드 코드하지 않고 오류 메시지에서 사용하기 위해 형식이나 멤버의 정규화되지 않은 문자열 이름을 가져올 수 있습니다.  이 기능을 사용하면 리팩터링할 때 코드를 올바르게 유지할 수 있습니다.  이 기능은 MVC\(Model\-View\-Controller\) 링크를 연결하고 속성 변경 이벤트를 발생시키는 데도 유용합니다.  
  
 [문자열 보간](../../csharp/language-reference/keywords/interpolated-strings.md)  
 문자열 보간 식을 사용하여 문자열을 생성할 수 있습니다.  보간된 문자열 식은 식이 포함된 템플릿 문자열과 유사합니다.  C\#에서는 식 결과의 ToString 표현으로 식을 대체하여 문자열을 만듭니다.  보간된 문자열은 인수 측면에서 [복합 형식 지정](../Topic/Composite%20Formatting.md)보다 이해하기 쉽습니다.  
  
 [Null 조건부 멤버 액세스 및 인덱싱](../../csharp/language-reference/operators/null-conditional-operators.md)  
 멤버 액세스\(`?.`\) 또는 인덱스\(`?[]`\) 작업을 수행하기 전에 매우 간단한 구문을 사용하여 null 테스트를 수행할 수 있습니다.  이러한 연산자는 null 검사의 처리를 위해 작성하는 코드의 양을 줄이는 데 도움이 되며 특히 데이터 구조에서 아래로 내려가는 경우에 유용합니다.  왼쪽 피연산자 또는 개체 참조가 null이면 연산에서 null이 반환됩니다.  
  
 [인덱스 이니셜라이저](../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 이제 사전 초기화와 같은 인덱싱을 지원하는 컬렉션의 특정 요소를 초기화할 수 있습니다.  
  
 [컬렉션 이니셜라이저 및 Add 확장 메서드](../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 컬렉션에 Add 확장 메서드가 있는 경우 이제 컬렉션에 이니셜라이저를 사용할 수 있습니다.  이전에는 Add 메서드가 인스턴스 메서드여야 했습니다.  
  
 **오버로드 확인**  
 더 많은 코드가 예상대로 작동할 수 있도록 컴파일러에서 오버로드 확인이 개선되었습니다.  문제 발견을 중지할 수 있는 경우는 nullable 값 형식을 사용하는 오버로드 중에서 선택하는 경우나 대리자를 사용하는 오버로드에 메서드 그룹\(람다 대신\)을 전달하는 경우입니다.  
  
 [예외 필터](../../csharp/language-reference/keywords/try-catch.md)  
 `catch` 절에서 예외 필터를 사용하여 catch 절에서 예외를 처리할지 여부를 결정할 수 있습니다.  이 기능을 사용하지 않으면 예외를 다시 throw해야 하는데 이 경우 다시 throw된 예외에서 보고된 호출 스택이 잘립니다.  
  
 [Catch 및 Finally 블록의 Await](../../csharp/language-reference/keywords/try-catch.md)  
 `catch` 및 `finally` 절에서 `await`를 사용할 수 있습니다.  
  
 [Auto 속성 이니셜라이저](../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
 이제 필드를 초기화하는 방법과 유사하게 Auto 속성을 초기화할 수 있습니다.  
  
 [Getter 전용 Auto 속성](../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
 전체 속성 구문을 사용하여 속성을 정의하지 않고도 이제 읽기 전용 Auto 속성을 정의할 수 있습니다.  속성을 선언하는 곳이나 형식의 생성자에서 속성을 초기화할 수 있습니다.  
  
 **식 본문을 사용하는 함수 멤버**  
 람다 식에 사용하는 동일한 간단한 구문으로 코드의 식 본문과 함께 멤버를 선언할 수 있습니다.  [메서드](../../fsharp/language-reference/members/methods.md), [속성](../../csharp/programming-guide/classes-and-structs/properties.md), [인덱서](../../csharp/programming-guide/indexers/index.md) 및 [오버로드할 수 있는 연산자](../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md)를 참조하세요.  
  
 [정적 형식 및 멤버 사용](../../csharp/language-reference/keywords/using-directive.md)  
 정적 형식의 액세스 가능한 정적 멤버를 가져와서 형식의 이름으로 액세스를 한정하지 않고 멤버를 참조할 수 있습니다.  
  
## 참고 항목  
 [Visual Studio 2015의 새로운 기능](/visual-studio/ide/what-s-new-in-visual-studio-2015)