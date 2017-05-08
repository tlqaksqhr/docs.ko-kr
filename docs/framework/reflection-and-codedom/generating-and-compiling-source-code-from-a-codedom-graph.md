---
title: "CodeDOM 그래프에서 소스 코드 생성 및 컴파일 | Microsoft Docs"
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
  - "어셈블리[.NET Framework], CodeDOM"
  - "코드 컴파일러"
  - "코드 문서 개체 모델, 소스 코드 생성"
  - "코드 문서 개체 모델, 그래프"
  - "코드 생성기"
  - "CodeDOM, 소스 코드 생성"
  - "CodeDOM, 그래프"
  - "어셈블리 컴파일"
  - "소스 코드 컴파일, 여러 가지 언어"
  - "동적 컴파일"
  - "동적으로 소스 코드 표시"
  - "CodeDOM 그래프 생성"
  - "여러 언어로 소스 코드 생성"
  - "CodeDOM으로 그래핑"
  - "CodeDOM에 의한 소스 코드 출력"
  - "소스 코드 생성"
  - "소스 코드, 생성"
  - "템플릿 기반 코드 생성"
  - "언어 간 변환"
ms.assetid: 6c864c8e-6dd3-4a65-ace0-36879d9a9c42
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# CodeDOM 그래프에서 소스 코드 생성 및 컴파일
<xref:System.CodeDom.Compiler> 네임스페이스의 경우 CodeDOM 개체 그래프를 기초로 소스 코드를 생성하고 지원되는 컴파일러를 통해 컴파일 관리에 사용할 수 있는 인터페이스가 제공됩니다.  코드 공급자를 사용하면 CodeDOM 그래프에 따라 특정 프로그래밍 언어로 소스 코드를 생성할 수 있습니다.  일반적으로 <xref:System.CodeDom.Compiler.CodeDomProvider>에서 파생되는 클래스의 경우 공급자에서 지원하는 언어에 대한 코드를 생성하고 컴파일하는 메서드를 제공할 수 있습니다.  
  
## CodeDOM 코드 공급자를 사용하여 소스 코드 생성  
 특정 언어로 소스 코드를 생성하려면 생성할 소스 코드 구조를 나타내는 CodeDOM 그래프가 있어야 합니다.  
  
 다음 예제에서는 <xref:Microsoft.CSharp.CSharpCodeProvider>의 인스턴스를 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[CodeDomExample#21](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#21)]
 [!code-csharp[CodeDomExample#21](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#21)]
 [!code-vb[CodeDomExample#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#21)]  
  
 코드 생성 그래프는 일반적으로 <xref:System.CodeDom.CodeCompileUnit>에 포함됩니다.  CodeDOM 그래프를 포함하는 **CodeCompileUnit**에 대한 코드를 생성하려면 코드 공급자의 <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 메서드를 호출합니다.  이 메서드에는 소스 코드 생성에 사용하는 <xref:System.IO.TextWriter>에 대한 매개 변수가 있어 작성 대상 **TextWriter**를 먼저 만들어야 할 때가 있습니다.  다음 예제에서는 **CodeCompileUnit**을 기초로 코드를 생성한 다음 생성된 소스 코드를 HelloWorld.cs라는 파일에 씁니다.  
  
 [!code-cpp[CodeDomExample#22](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#22)]
 [!code-csharp[CodeDomExample#22](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#22)]
 [!code-vb[CodeDomExample#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#22)]  
  
## CodeDOM 코드 공급자를 사용하여 어셈블리 컴파일  
 **컴파일 호출**  
  
 CodeDom 공급자를 사용하여 어셈블리를 컴파일하려면 컴파일러 대상 언어로 컴파일할 소스 코드 또는 컴파일 대상 소스 코드를 생성할 수 있는 CodeDOM 그래프가 있어야 합니다.  
  
 CodeDOM 그래프를 기초로 컴파일하려는 경우에는 해당 그래프가 포함된 <xref:System.CodeDom.CodeCompileUnit>을 코드 공급자의 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A> 메서드로 전달해야 합니다.  컴파일러에서 식별하는 언어의 소스 코드 파일이 있으면 소스 코드가 들어 있는 파일 이름을 CodeDom 공급자의 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> 메서드에 전달합니다.  또한 컴파일러에서 식별하는 언어의 소스 코드가 들어 있는 문자열을 CodeDom 공급자의 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A> 메서드에 전달할 수 있습니다.  
  
 **컴파일 매개 변수 구성**  
  
 CodeDom 공급자의 모든 표준 컴파일 호출 메서드에는 컴파일에 사용되는 옵션을 지정하는 <xref:System.CodeDom.Compiler.CompilerParameters> 형식의 매개 변수가 있습니다.  
  
 출력 어셈블리의 파일 이름은 **CompilerParameters**의 <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A> 속성으로 지정할 수 있습니다.  그렇지 않을 경우 기본 출력 파일 이름이 사용됩니다.  
  
 기본적으로 새 **CompilerParameters**는 <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A> 속성을 **false**로 설정하여 초기화합니다.  실행 프로그램을 컴파일하는 경우에는 **GenerateExecutable** 속성을 **true**로 설정해야 합니다.  **GenerateExecutable**을 **false**로 설정하면 컴파일러는 클래스 라이브러리를 생성합니다.  
  
 CodeDOM 그래프에서 실행 파일을 컴파일하는 경우 <xref:System.CodeDom.CodeEntryPointMethod>가 그래프에 정의되어야 합니다.  코드 진입점이 여러 개인 경우 **CompilerParameters**의 <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A> 속성을 사용 대상 진입점을 정의하는 클래스 이름으로 설정해야 합니다.  
  
 생성되는 실행 파일에 디버그 정보를 포함시키려면 <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A> 속성을 **true**로 설정합니다.  
  
 프로젝트에서 어셈블리를 참조하는 경우 컴파일을 호출할 때 사용하는 **CompilerParameters**의 <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A> 속성과 같이 어셈블리 이름을 <xref:System.Collections.Specialized.StringCollection>의 항목으로 지정해야 합니다.  
  
 <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A> 속성을 **true**로 설정해서 디스크가 아니라 메모리에 기록되는 어셈블리를 컴파일할 수 있습니다.  어셈블리가 메모리에서 생성되면, 코드는 생성된 어셈블리에 대한 참조를 <xref:System.CodeDom.Compiler.CompilerResults>의 <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A> 속성에서 가져올 수 있습니다.  어셈블리가 디스크에 쓰여지면 생성된 어셈블리에 대한 경로를 **CompilerResults**의 <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A> 속성에서 가져올 수 있습니다.  
  
 컴파일 프로세스를 호출할 때 사용할 사용자 지정 명령줄 인수 문자열을 지정하려면, <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> 속성에서 문자열을 설정합니다.  
  
 Win32 보안 토큰이 컴파일러 프로세스를 호출하는 데 필요하면 <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A> 속성에서 토큰을 지정합니다.  
  
 Win32 리소스 파일을 컴파일된 어셈블리에 연결하려면 <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A> 속성에서 Win32 리소스 파일의 이름을 지정합니다.  
  
 컴파일을 중단할 경고 수준을 지정하려면 컴파일을 중단할 경고 수준을 나타내는 정수로 <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A> 속성을 설정합니다.  또한 <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A> 속성을 **true**로 설정해서 경고가 발생한 경우 컴파일을 중단하도록 컴파일러를 구성할 수도 있습니다.  
  
 다음 코드 예제에서는 <xref:System.CodeDom.Compiler.CodeDomProvider> 클래스에서 파생된 CodeDom 공급자를 사용하여 소스 파일을 컴파일하는 방법을 보여 줍니다.  
  
 [!code-cpp[CodeDomExample#23](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#23)]
 [!code-csharp[CodeDomExample#23](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#23)]
 [!code-vb[CodeDomExample#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#23)]  
  
## 지원되는 언어  
 .NET Framework에서는 C\#, Visual Basic, C\+\+ 및 JScript에 대한 코드 컴파일러 및 코드 생성기를 제공합니다.  언어별 코드 생성기나 코드 컴파일러를 구현하면 다른 언어도 지원하도록 CodeDOM을 확장할 수 있습니다.  
  
## 참고 항목  
 <xref:System.CodeDom>   
 <xref:System.CodeDom.Compiler>   
 [동적 소스 코드 생성 및 컴파일](../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)   
 [CodeDOM Quick Reference](http://msdn.microsoft.com/ko-kr/c77b8bfd-0a32-4e36-b59a-4f687f32c524)