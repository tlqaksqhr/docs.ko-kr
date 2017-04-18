---
title: "CodeDOM 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "코드 컴파일러"
  - "코드 문서 개체 모델"
  - "코드 문서 개체 모델, 그래프"
  - "코드 생성기"
  - "CodeDOM"
  - "CodeDOM, 그래프"
  - "동적 컴파일"
  - "동적으로 소스 코드 표시"
  - "CodeDOM으로 그래핑"
  - "네임스페이스[.NET Framework], CodeDOM"
  - "소스 코드 모델"
  - "템플릿 기반 코드 생성"
  - "형식, CodeDOM"
ms.assetid: 0444ddf3-c3f6-44ed-a999-f710d9c3e0cf
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# CodeDOM 사용
CodeDOM에서는 소스 코드 요소의 수많은 공용 형식을 나타낼 수 있는 형식을 제공합니다.  CodeDOM 요소로 개체 그래프를 어셈블하여 소스 코드 모델을 빌드하도록 프로그램을 디자인할 수 있습니다.  이 개체 그래프는 지원되는 프로그래밍 언어에 대한 CodeDOM 코드 생성기를 사용하여 소스 코드로 렌더링될 수 있습니다.  또한 CodeDOM을 사용하여 소스 코드를 이진 어셈블리로 컴파일할 수 있습니다.  
  
 CodeDOM은 일반적으로 다음과 같은 경우에 사용합니다.  
  
-   템플릿 기반 코드 생성: ASP.NET, XML Web services의 클라이언트 프록시, 코드 마법사, 디자이너 또는 코드를 내보내는 기타 메커니즘 등에 대한 코드를 생성합니다.  
  
-   동적 컴파일링: 코드를 한 가지 또는 여러 가지 언어로 컴파일합니다.  
  
## CodeDOM 그래프 빌드  
 <xref:System.CodeDom> 네임스페이스는 언어 구문에 관계없이 소스 코드의 논리적 구조를 나타내는 클래스를 제공합니다.  
  
### CodeDOM 그래프 구조  
 CodeDOM 그래프 구조는 컨테이너 트리와 비슷합니다.  컴파일할 수 있는 각 CodeDOM 그래프의 맨 위 또는 루트 컨테이너는 <xref:System.CodeDom.CodeCompileUnit>입니다.  소스 코드 모델의 모든 요소는 그래프에 있는 <xref:System.CodeDom.CodeObject>의 속성을 통해 그래프로 연결되어야 합니다.  
  
### 샘플 Hello World 프로그램에 대한 소스 코드 모델 빌드  
 다음 연습에서는 간단한 Hello World 응용 프로그램의 코드를 나타내는 CodeDOM 개체 그래프를 빌드하는 방법을 보여 줍니다.  이 코드 예제의 전체 소스 코드를 보려면 <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=fullName> 항목을 참조하십시오.  
  
#### 컴파일 단위 만들기  
 CodeDOM은 <xref:System.CodeDom.CodeCompileUnit>이라는 개체를 정의하는데, 이 단위는 컴파일할 소스 코드를 모델링하는 CodeDOM 개체 그래프를 참조할 수 있습니다.  **CodeCompileUnit**에는 특성, 네임스페이스 및 어셈블리에 대한 참조 저장을 위한 속성이 있습니다.  
  
 <xref:System.CodeDom.Compiler.CodeDomProvider> 클래스에서 파생되는 CodeDom 공급자는 **CodeCompileUnit**에서 참조하는 개체 그래프를 처리하는 메서드를 포함합니다.  
  
 간단한 응용 프로그램에 대한 개체 그래프를 만들려면 소스 코드를 어셈블한 다음 **CodeCompileUnit**에서 이를 참조하도록 해야 합니다.  
  
 이 예제에 있는 구문을 사용하여 새 컴파일 단위를 만들 수 있습니다.  
  
 [!code-cpp[CodeDomExample#12](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#12)]
 [!code-csharp[CodeDomExample#12](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#12)]
 [!code-vb[CodeDomExample#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#12)]  
  
 <xref:System.CodeDom.CodeSnippetCompileUnit>은 이미 대상 언어로 되어 있지만 다른 언어로 렌더링될 수 없는 소스 코드의 일부를 포함할 수 있습니다.  
  
#### 네임스페이스 정의  
 네임스페이스를 정의하려면 먼저 <xref:System.CodeDom.CodeNamespace>를 만든 다음 적절한 생성자를 사용하거나 해당 **NamName** 속성을 설정하여 이름을 할당합니다.  
  
 [!code-cpp[CodeDomExample#13](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#13)]
 [!code-csharp[CodeDomExample#13](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#13)]
 [!code-vb[CodeDomExample#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#13)]  
  
#### 네임스페이스 가져오기  
 네임스페이스에 네임스페이스 가져오기 지시문을 추가하려면 가져올 네임스페이스를 나타내는 <xref:System.CodeDom.CodeNamespaceImport>를 **CodeNamespace.Imports** 컬렉션에 추가합니다.  
  
 다음 코드에서는 `samples`라는 **CodeNamespace**의 **Imports** 컬렉션에 **System** 네임스페이스에 대한 가져오기를 추가합니다.  
  
 [!code-cpp[CodeDomExample#14](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#14)]
 [!code-csharp[CodeDomExample#14](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#14)]
 [!code-vb[CodeDomExample#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#14)]  
  
#### 코드 요소를 개체 그래프에 연결  
 CodeDOM 그래프를 구성하는 모든 코드 요소는 그래프의 루트 개체 속성으로부터 직접적으로 참조되는 요소들 사이의 일련의 참조에 의해 트리의 루트 요소인 <xref:System.CodeDom.CodeCompileUnit>에 연결되어야 합니다.  우선 컨테이너 개체의 속성에 대한 개체를 설정하여 컨테이너 개체로부터의 참조를 만듭니다.  
  
 다음 문에서는 루트 **CodeCompileUnit**의 **Namespaces** 컬렉션 속성에 `samples` **CodeNamespace**를 추가합니다.  
  
 [!code-cpp[CodeDomExample#15](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#15)]
 [!code-csharp[CodeDomExample#15](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#15)]
 [!code-vb[CodeDomExample#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#15)]  
  
#### 형식 정의  
 CodeDOM을 사용하여 클래스, 구조체, 인터페이스 또는 열거형을 선언하려면 새 <xref:System.CodeDom.CodeTypeDeclaration>을 만든 다음 이름을 할당합니다.  다음 예제에서는 생성자 오버로드를 사용하여 **Name** 속성을 설정하는 방법을 보여 줍니다.  
  
 [!code-cpp[CodeDomExample#16](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#16)]
 [!code-csharp[CodeDomExample#16](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#16)]
 [!code-vb[CodeDomExample#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#16)]  
  
 네임스페이스에 형식을 추가하려면 네임스페이스에 추가하는 형식을 나타내는 <xref:System.CodeDom.CodeTypeDeclaration>을 **CodeNamespace**의 **Types** 컬렉션에 추가합니다.  
  
 다음 예제에서는 `samples`라는 **CodeNamespace**에 `class1`이라는 이름의 클래스를 추가하는 방법을 보여 줍니다.  
  
 [!code-cpp[CodeDomExample#17](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#17)]
 [!code-csharp[CodeDomExample#17](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#17)]
 [!code-vb[CodeDomExample#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#17)]  
  
#### 클래스에 클래스 멤버 추가하기  
 <xref:System.CodeDom> 네임스페이스는 클래스 멤버를 나타내는데 사용할 수 있는 여러 요소를 제공합니다.  각 클래스 멤버는 <xref:System.CodeDom.CodeTypeDeclaration>의 **Members** 컬렉션에 추가될 수 있습니다.  
  
#### 실행 파일에 대한 코드 진입점 정의  
 실행 프로그램의 코드를 빌드하는 경우에는 프로그램 실행이 시작해야 하는 메서드를 나타내기 위한 <xref:System.CodeDom.CodeEntryPointMethod>를 만들어서 프로그램의 진입점을 나타내야 합니다.  
  
 다음 예제에서는 "Hello World\!"를 인쇄하는 **System.Console.WriteLine**을 호출하는 <xref:System.CodeDom.CodeMethodInvokeExpression>이 포함된 진입점 메서드를 정의하는 방법을 보여 줍니다.  
  
 [!code-cpp[CodeDomExample#18](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#18)]
 [!code-csharp[CodeDomExample#18](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#18)]
 [!code-vb[CodeDomExample#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#18)]  
  
 다음 문에서는 `class1`의 **Members** 컬렉션에 `Start`라는 진입점 메서드를 추가합니다.  
  
 [!code-cpp[CodeDomExample#19](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source2.cpp#19)]
 [!code-csharp[CodeDomExample#19](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source2.cs#19)]
 [!code-vb[CodeDomExample#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source2.vb#19)]  
  
 이제 `compileUnit`이라는 <xref:System.CodeDom.CodeCompileUnit>에 간단한 Hello World 프로그램에 대한 CodeDOM 그래프가 포함됩니다.  CodeDOM 그래프에서 코드를 생성 및 컴파일하는 방법에 대한 자세한 내용은 [소스 코드 생성 및 CodeDOM 그래프에서 프로그램 컴파일](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)을 참조하십시오.  
  
### CodeDOM 그래프 빌드에 대한 추가 정보  
 대신 공용 언어 런타임을 지원하는 프로그래밍 언어에서 주로 사용되는 다양한 유형의 코드 요소를 지원합니다.  CodeDOM은 사용 가능한 프로그래밍 언어의 모든 기능을 나타낼 수 있는 요소를 제공하지는 못합니다.  CodeDOM 요소로 쉽게 나타낼 수 없는 코드는 <xref:System.CodeDom.CodeSnippetExpression>, <xref:System.CodeDom.CodeSnippetStatement>, <xref:System.CodeDom.CodeSnippetTypeMember> 또는 <xref:System.CodeDom.CodeSnippetCompileUnit>에 캡슐화할 수 있습니다.  그러나 코드 조각은 CodeDOM을 통해 다른 언어로 자동 변환될 수 없습니다.  
  
 각 CodeDOM 형식에 대한 자세한 내용은 <xref:System.CodeDom> 네임스페이스에 대한 참조 설명서를 참조하십시오.  
  
 특정 형식의 코드 요소를 나타내는 CodeDOM 요소의 위치를 보여 주는 차트를 보려면 [CodeDOM Quick Reference](http://msdn.microsoft.com/ko-kr/c77b8bfd-0a32-4e36-b59a-4f687f32c524)를 참조하십시오.