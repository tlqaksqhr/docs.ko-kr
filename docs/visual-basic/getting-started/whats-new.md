---
title: "Visual Basic의 새로운 기능 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- VB.StartPage.WhatsNew
dev_langs:
- VB
helpviewer_keywords:
- new features, Visual Basic
- what's new [Visual Basic]
- Visual Basic, what's new
ms.assetid: d7e97396-7f42-4873-a81c-4ebcc4b6ca02
caps.latest.revision: 145
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 55cf69a06a047c12f027007ed7180bf74307f2c9
ms.lasthandoff: 03/13/2017

---
# <a name="whats-new-for-visual-basic"></a>Visual Basic의 새로운 기능
이 페이지에는 각 Visual Basic 버전의 주요 기능 이름과 최신 Visual Basic 버전의 새로운 기능 및 향상된 기능에 대한 설명이 정리되어 있습니다.  
  
## <a name="previous-versions"></a>이전 버전  
 Visual Basic / Visual Studio .NET 2002  
 첫 번째 릴리스  
  
 Visual Basic / Visual Studio .NET 2003  
 비트 시프트 연산자, 루프 변수 선언  
  
 Visual Basic / Visual Studio .NET 2005  
 `My` 형식 및 도우미 형식(앱, 컴퓨터, 파일 시스템, 네트워크에 액세스)  
  
 Visual Basic / Visual Studio .NET 2008  
 LINQ(통합 언어 쿼리), XML 리터럴, 지역 형식 유추, 개체 이니셜라이저, 익명 형식, 확장 메서드, 로컬 `var` 형식 유추, 람다 식, `if` 연산자, 부분 메서드(Partial Method), nullable 값 형식  
  
 Visual Basic, Visual Studio .NET 2010  
 자동으로 구현된 속성, 컬렉션 이니셜라이저, 암시적 줄 연속, 동적, 제네릭 공변성(Covariance)/반공변성(Contravariance), 전역 네임스페이스 액세스  
  
 Visual Basic / Visual Studio .NET 2012  
 `Async` / `await`, 반복기, 호출자 정보 특성  
  
 Visual Basic / Visual Studio .NET 2013  
 .NET 컴파일러 플랫폼 ("Roslyn")의 기술 미리 보기  
  
 Visual Basic / Visual Studio .NET 2015  
 현재 버전, 아래 참조  
  
## <a name="current-version"></a>현재 버전  
 [Nameof](../../csharp/language-reference/keywords/nameof.md)  
 문자열을 하드 코드하지 않고 오류 메시지에서 사용하기 위해 형식이나 멤버의 정규화되지 않은 문자열 이름을 가져올 수 있습니다.  이 기능을 사용하면 리팩터링할 때 코드를 올바르게 유지할 수 있습니다.  이 기능은 MVC(Model-View-Controller) 링크를 연결하고 속성 변경 이벤트를 발생시키는 데도 유용합니다.  
  
 [문자열 보간](../../csharp/language-reference/keywords/interpolated-strings.md)  
 문자열 보간 식을 사용하여 문자열을 생성할 수 있습니다.  보간된 문자열 식은 식이 포함된 템플릿 문자열과 유사합니다.  보간된 문자열은 인수 측면에서 [Composite Formatting](../../standard/base-types/composite-format.md)보다 이해하기 쉽습니다.  
  
 [Null 조건부 멤버 액세스 및 인덱싱](../../csharp/language-reference/operators/null-conditional-operators.md)  
 멤버 액세스(`?.`) 또는 인덱스(`?[]`) 작업을 수행하기 전에 매우 간단한 구문을 사용하여 null 테스트를 수행할 수 있습니다.  이러한 연산자는 null 검사의 처리를 위해 작성하는 코드의 양을 줄이는 데 도움이 되며 특히 데이터 구조에서 아래로 내려가는 경우에 유용합니다.  왼쪽 피연산자 또는 개체 참조가 null이면 연산에서 null이 반환됩니다.  
  
 [다중 선 문자열 리터럴](../../visual-basic/programming-guide/language-features/strings/string-basics.md)  
 문자열 리터럴에 줄 바꿈 시퀀스가 포함될 수 있습니다.  `<xml><![CDATA[...text with newlines...]]></xml>.Value` 사용과 관련된 이전 작업은 더 이상 필요하지 않습니다.  
  
 설명  
 암시적 줄 연속 뒤, 이니셜라이저 식 내부 및 LINQ 식 항 사이에 주석을 입력할 수 있습니다.  
  
 더 효율적인 정규화된 이름 확인  
 `Threading.Thread.Sleep(1000)`과 같은 코드가 제공된 경우 이전에는 Visual Basic에서 "Threading" 네임스페이스를 조회하고 System.Threading 및 System.Windows.Threading 간에 모호하다는 사실을 발견한 후 오류를 보고했습니다.  이제 Visual Basic에서는 두 가지 가능한 네임스페이스를 함께 고려합니다.  완성 목록을 표시하는 경우 Visual Studio 편집기에서 두 형식의 멤버가 모두 완성 목록에 나열됩니다.  
  
 연도가 먼저 나오는 날짜 리터럴  
 yyyy-mm-dd 형식(`#2015-03-17 16:10 PM#`)의 날짜 리터럴을 사용할 수 있습니다.  
  
 읽기 전용 인터페이스 속성  
 읽기/쓰기 속성을 사용하여 읽기 전용 인터페이스 속성을 구현할 수 있습니다.  이러한 인터페이스는 최소 기능을 보장하며 구현 클래스에서 속성이 설정되도록 허용하는 것을 차단하지 않습니다.  
  
 [TypeOf \<expr> IsNot \<type>](../../visual-basic/language-reference/operators/typeof-operator.md)  
 코드를 더 읽기 쉽게 만들기 위해 `IsNot`과 함께 `TypeOf`를 사용할 수 있습니다.  
  
 [#Disable Warning \<ID> 및 #Enable Warning \<ID>](../../visual-basic/language-reference/directives/directives.md)  
 소스 파일 내의 영역에 대한 특정 경고를 사용하지 않거나 사용하도록 설정할 수 있습니다.  
  
 XML 문서 주석 향상  
 문서 주석을 작성하면 편집기의 효율성을 높이고 매개 변수 이름의 유효성 검사, `crefs`(제네릭, 연산자 등)의 적절한 처리, 색 지정 및 리팩터링에 대한 지원을 제공할 수 있습니다.  
  
 [부분 모듈 및 인터페이스 정의](../../visual-basic/language-reference/modifiers/partial.md)  
 클래스 및 구조체 외에도 부분 모듈과 인터페이스를 선언할 수 있습니다.  
  
 [메서드 본문 내의 #Region 지시문](../../visual-basic/language-reference/directives/region-directive.md)  
 #Region…#End Region 구분 기호를 파일의 원하는 위치, 함수 내부 및 여러 함수 본문을 포괄하여 입력할 수 있습니다.  
  
 [Overrides 정의는 암시적으로 Overloads임](../../visual-basic/language-reference/modifiers/overrides.md)  
 `Overrides` 한정자를 정의에 추가하면 일반적인 경우에 더 적은 코드를 입력할 수 있도록 컴파일러에서 암시적으로 `Overloads`를 추가합니다.  
  
 특성 인수에서 허용되는 CObj  
 이전에는 컴파일러에서 CObj(...)가 특성 생성에서 사용될 때 상수가 아니라는 오류를 제공했습니다.  
  
 여러 인터페이스의 모호한 메서드 선언 및 사용  
 이전에는 다음 코드에서 `IMock`을 선언하거나 `GetDetails`를 호출하지 못하게 하는 오류가 발생했습니다(이러한 항목이 C#에서 선언된 경우).  
  
```vb  
Interface ICustomer  
  Sub GetDetails(x As Integer)  
End Interface  
  
Interface ITime  
  Sub GetDetails(x As String)  
End Interface  
  
Interface IMock : Inherits ICustomer, ITime  
  Overloads Sub GetDetails(x As Char)  
End Interface  
  
Interface IMock2 : Inherits ICustomer, ITime  
End Interface  
  
```  
  
 이제 컴파일러에서 일반 오버로드 확인 규칙을 사용하여 호출하는 데 가장 적합한 `GetDetails`를 선택하며, 샘플에서와 같이 Visual Basic에서 인터페이스 관계를 선언할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 2017의 새로운 기능](https://docs.microsoft.com/en-us/visualstudio/ide/whats-new-in-visual-studio)
