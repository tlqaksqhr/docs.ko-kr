---
title: "최선의 예외 구현 방법 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "예외, 유용한 정보"
ms.assetid: f06da765-235b-427a-bfb6-47cd219af539
caps.latest.revision: 28
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 28
---
# 최선의 예외 구현 방법
잘 설계된 응용 프로그램이 응용 프로그램 충돌을 방지하기 위해 예외와 오류를 처리합니다.  이 자료에서는 예외를 처리하고 만들기 위한 최선의 방법을 설명합니다.  
  
## 예외 처리  
 다음 목록에는 응용 프로그램의 예외를 처리하기 위한 일반적인 지침이 있습니다.  
  
-   예외 처리 코드\(`try`\/`catch` 블록\)를 적절하게 사용합니다.  발생 가능성이 있는 조건을 예외 처리를 사용하지 않고 프로그래밍 방식으로 검사할 수도 있습니다.  
  
     **프로그래밍 방식 검사**.  다음 예제에서는 `if` 문을 사용하여 연결이 끊어졌는지를 검사합니다.  이 예제에서는 연결이 끊어지지 않은 경우 예외를 throw하는 대신 연결을 끊습니다.  
  
     [!code-cpp[Conceptual.Exception.Handling#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#2)]
     [!code-csharp[Conceptual.Exception.Handling#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#2)]
     [!code-vb[Conceptual.Exception.Handling#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#2)]  
  
     **예외 처리**.  연결이 종료되지 않는 경우, 다음 예제에서는 `try`\/`catch` 블록을 사용하여 연결을 확인하고 예외를 throw합니다.  
  
     [!code-cpp[Conceptual.Exception.Handling#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#3)]
     [!code-csharp[Conceptual.Exception.Handling#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#3)]
     [!code-vb[Conceptual.Exception.Handling#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#3)]  
  
     어떤 방법을 선택할 것인지는 해당 이벤트의 발생 빈도에 따라 달라집니다.  
  
    -   이벤트가 그다지 자주 발생하지 않으면\(즉, 예상치 못한 파일 끝과 같은 이벤트가 실제로 예외이고 오류를 나타내는 경우\) 예외 처리를 사용합니다.  예외 처리를 사용하면 정상적인 조건에서 적은 수의 코드가 실행됩니다.  
  
    -   이벤트가 일상적으로 발생하고 정상적인 실행의 일부로 간주될 수 있는 경우 프로그래밍 방식의 메서드를 사용하여 오류를 검사합니다.  프로그래밍 방식으로 오류를 확인할 때, 예외가 발생하는 경우 더 많은 코드가 실행됩니다.  
  
-   잠재적으로 예외를 생성할 수 있는 코드 주위에 `try`\/`catch` 블록을 사용하고, 필요한 경우 `finally` 블록을 사용하여 리소스를 정리합니다.  이 방법으로 `try` 문은 예외를 생성하고, `catch` 문은 예외를 처리하며, `finally` 문은 예외의 발생 여부와 상관없이 리소스를 닫거나 할당 해제합니다.  
  
-   `catch` 블록에서 항상 가장 특정한 예외부터 가장 일반적인 예외의 순서로 예외를 지정합니다.  이렇게 하면 특정 예외가 더 일반적인 `catch` 블록으로 전달되기 전에 먼저 처리됩니다.  
  
## 예외 만들기 및 발생  
 다음 목록에는 자체적인 예외를 만들기 위한 지침과 이런 예외가 발생되어야 하는 시점이 나와 있습니다.  자세한 내용은 [예외에 대 한 디자인 지침](../../../docs/standard/design-guidelines/exceptions.md)을 참조하세요.  
  
-   일반적인 사용에서는 예외가 throw되지 않도록 클래스를 디자인합니다.  예를 들어, <xref:System.IO.FileStream> 클래스는 파일 끝에 도달했는지 확인하는 데 도움이 되는 메서드를 제공합니다.  이렇게 하면 파일 끝 이후의 부분을 읽을 때 오류가 throw되는 것을 방지할 수 있습니다.  다음 예제에서는 파일 끝까지 읽는 방법을 보여 줍니다.  
  
     [!code-cpp[Conceptual.Exception.Handling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#5)]
     [!code-csharp[Conceptual.Exception.Handling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#5)]
     [!code-vb[Conceptual.Exception.Handling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#5)]  
  
-   오류 코드 또는 HRESULT를 반환하는 대신 예외를 throw합니다.  
  
-   지극히 일반적인 오류 발생 사례에 대해 예외를 throw하는 대신 null을 반환합니다.  매우 흔한 오류 사례는 정상적인 제어 흐름으로 간주할 수 있습니다.  이러한 경우에 null을 반환함으로써, 응용 프로그램의 성능에 미치는 영향을 최소화합니다.  
  
-   대부분의 경우, 미리 정의된 .NET Framework 예외 형식을 사용합니다.  새 예외 클래스는 미리 정의된 예외 클래스가 적용되지 않는 경우에만 도입합니다.  
  
-   개체의 현재 상태에서 속성 집합이나 메서드 호출이 적절하지 않을 경우 <xref:System.InvalidOperationException> 예외를 throw합니다.  
  
-   잘못된 매개 변수가 전달되면 <xref:System.ArgumentException>에서 파생된 클래스 또는 <xref:System.ArgumentException> 예외를 throw합니다.  
  
-   대부분의 응용 프로그램에서는 <xref:System.Exception> 클래스에서 사용자 지정 예외를 파생시킵니다.  <xref:System.ApplicationException> 클래스에서 파생하면 중요한 값이 추가되지 않습니다.  
  
-   예외 클래스의 이름 뒤에는 "Exception"을 붙입니다.  예를 들면 다음과 같습니다.  
  
     [!code-cpp[Conceptual.Exception.Handling#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#4)]
     [!code-csharp[Conceptual.Exception.Handling#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#4)]
     [!code-vb[Conceptual.Exception.Handling#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#4)]  
  
-   C\# 및 C\+\+에서는 사용자 고유의 예외 클래스를 만들 때 세 개 이상의 공통 생성자를 사용합니다. 이런 공통 생성자는 기본 생성자, 문자열 메시지를 취하는 생성자, 문자열 메시지와 내부 예외를 취하는 생성자입니다.  예제를 보려면 [방법: 사용자 정의 예외 만들기](../../../docs/standard/exceptions/how-to-create-user-defined-exceptions.md)를 참조하십시오.  
  
    1.  기본값을 사용하는 <xref:System.Exception.%23ctor>.  
  
    2.  문자열 메시지를 수락하는 <xref:System.Exception.%23ctor%28System.String%29>.  
  
    3.  문자열 메시지와 내부 예외를 허용하는 <xref:System.Exception.%23ctor%28System.String%2CSystem.Exception%29>.  
  
-   사용자 정의 예외를 만들 때, 여러 응용 프로그램 도메인에서 예외가 발생할 때뿐만 아니라 원격에서 실행되는 코드에서도 해당 예외에 대한 메타데이터를 사용할 수 있도록 만들어야 합니다.  예를 들어, 응용 프로그램 도메인 A에서 예외를 throw하는 코드를 실행하는 응용 프로그램 도메인 B를 만든다고 가정합니다.  응용 프로그램 도메인 A에서 예외를 정확하게 catch하고 처리하려면 응용 프로그램 도메인 B에서 throw된 예외를 포함하는 어셈블리를 찾을 수 있어야 합니다.  응용 프로그램 도메인 B에서 응용 프로그램 도메인 A의 응용 프로그램 기본 구조가 아닌 자신의 기본 구조에 있는 어셈블리에 포함된 예외를 throw하면 응용 프로그램 도메인 A에서는 해당 예외를 찾을 수 없으며 공용 언어 런타임은 <xref:System.IO.FileNotFoundException> 예외를 throw합니다.  이러한 상황을 방지하기 위해 예외 정보가 포함된 어셈블리를 다음과 같은 두 가지 방법으로 배포할 수 있습니다.  
  
    -   해당 어셈블리를 두 응용 프로그램 도메인이 공유하는 공통 응용 프로그램 기본 구조에 넣습니다.  
  
         또는  
  
    -   도메인이 공통 응용 프로그램 기반 구조를 공유하지 않을 경우, 예외 정보가 포함된 어셈블리를 강력한 이름으로 지정한 다음, 이 어셈블리를 전역 어셈블리 캐시에 배포합니다.  
  
-   모든 예외에는 지역화된 설명 문자열을 포함시킵니다.  사용자에게 표시되는 오류 메시지는 예외 클래스에서 파생된 메시지가 아니라, throw된 예외의 설명 문자열에서 파생된 메시지입니다.  
  
-   문법적으로 올바른 오류 메시지와 구두점을 사용합니다.  설명 문자열의 각 문장의 뒤에는 마침표가 있어야 합니다.  예를 들어, "로그 테이블이 오버플로되었습니다."가 적절한 설명 문자열입니다.  
  
-   프로그래밍 액세스에는 <xref:System.Exception> 속성을 제공합니다.  추가 정보가 유용한 프로그래밍 시나리오에 대해서만 예외에 설명 문자열 이외의 추가 속성을 제공합니다.  예를 들어, <xref:System.IO.FileNotFoundException>은 <xref:System.IO.FileNotFoundException.FileName%2A> 속성을 제공합니다.  
  
-   스택 추적은 예외가 throw되는 문에서 시작하여 예외를 catch하는 `catch` 문까지 수행됩니다.  `throw` 문을 사용할 위치를 결정할 때 이러한 점에 주의하십시오.  
  
-   예외 작성기 메서드를 사용합니다.  클래스는 구현된 여러 위치에서 동일한 예외를 throw하는 것이 일반적입니다.  코드를 많이 사용하지 않으려면 예외를 만들어 반환하는 도우미 메서드를 사용합니다.  예를 들면 다음과 같습니다.  
  
     [!code-cpp[Conceptual.Exception.Handling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.exception.handling/cpp/source.cpp#6)]
     [!code-csharp[Conceptual.Exception.Handling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.exception.handling/cs/source.cs#6)]
     [!code-vb[Conceptual.Exception.Handling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.exception.handling/vb/source.vb#6)]  
  
     또는 예외의 생성자를 사용하여 예외를 만듭니다.  <xref:System.ArgumentException>과 같은 전역 예외 클래스에는 이 방법이 더 적합합니다.  
  
-   예외를 throw할 때 중간 결과를 정리합니다.  호출자가 메서드에서 예외가 throw될 때 의도하지 않은 결과가 발생하지 않는다고 가정할 수 있어야 합니다.  
  
## 참고 항목  
 [예외](../../../docs/standard/exceptions/index.md)