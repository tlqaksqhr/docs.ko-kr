---
title: "방법: CodeDOM을 사용하여 클래스 만들기 | Microsoft Docs"
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
  - "코드 문서 개체 모델, 클래스 만들기"
  - "코드 문서 개체 모델, 그래프"
  - "CodeDOM, 클래스 만들기"
  - "CodeDOM, 그래프"
  - "CodeDOM으로 그래핑"
ms.assetid: 0ceb70fe-36e1-49bb-922b-e9f615c20a14
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: CodeDOM을 사용하여 클래스 만들기
다음 절차에서는 CodeDOM 그래프를 만들고 컴파일하는 방법을 보여 줍니다. 이 CodeDOM 그래프는 두 개의 필드 및 세 개의 속성과 메서드, 생성자 및 진입점이 각각 한 개씩 들어 있는 클래스를 생성합니다.  
  
1.  CodeDOM 코드를 사용하여 클래스의 소스 코드를 생성할 콘솔 응용 프로그램을 만듭니다.  
  
     이 예제에서 생성하는 클래스는 `Sample`이고 생성되는 코드는 SampleCode 파일의 `CodeDOMCreatedClass` 클래스입니다.  
  
2.  생성하는 클래스에서 CodeDOM 그래프를 초기화하고 CodeDOM 메서드를 사용하여 생성되는 클래스의 멤버, 생성자 및 진입점\(`Main` 메서드\)을 정의합니다.  
  
     이 예제에서 생성되는 클래스에는 두 개의 필드및 세 개의 속성과 각각 한 개씩의 생성자, 메서드 및 `Main` 메서드가 포함됩니다.  
  
3.  생성하는 클래스에서 언어별 코드 공급자를 만들고 이 공급자의 <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 메서드를 호출하여 그래프에서 코드를 생성합니다.  
  
4.  응용 프로그램을 컴파일하고 실행하여 코드를 생성합니다.  
  
     이 예제에서 생성되는 코드는 SampleCode 파일에 있습니다.  이 코드를 컴파일하고 실행하여 샘플 출력을 확인합니다.  
  
### CodeDOM 코드를 실행할 응용 프로그램을 만들려면  
  
-   CodeDOM 코드를 포함할 콘솔 응용 프로그램 클래스를 만듭니다.  해당 클래스에서 어셈블리\(<xref:System.CodeDom.CodeCompileUnit>\)와 클래스\(<xref:System.CodeDom.CodeTypeDeclaration>\)를 참조하는 데 사용할 전역 필드를 정의하고, 생성되는 소스 파일의 이름을 지정하고, `Main` 메서드를 선언합니다.  
  
     [!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]
     [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]  
  
### CodeDOM 그래프를 초기화하려면  
  
-   콘솔 응용 프로그램 클래스의 생성자에서 어셈블리와 클래스를 초기화하고 CodeDOM 그래프에 적절한 선언을 추가합니다.  
  
     [!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]
     [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]  
  
### CodeDOM 그래프에 멤버를 추가하려면  
  
-   클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeMemberField> 개체를 추가하여 CodeDOM 그래프에 필드를 추가합니다.  
  
     [!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]
     [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]  
  
-   클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeMemberProperty> 개체를 추가하여 CodeDOM 그래프에 속성을 추가합니다.  
  
     [!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]
     [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]  
  
-   클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeMemberMethod> 개체를 추가하여 CodeDOM 그래프에 메서드를 추가합니다.  
  
     [!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]
     [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]  
  
-   클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeConstructor> 개체를 추가하여 CodeDOM 그래프에 생성자를 추가합니다.  
  
     [!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]
     [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]  
  
-   클래스의 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 속성에 <xref:System.CodeDom.CodeEntryPointMethod> 개체를 추가하여 CodeDOM 그래프에 진입점을 추가합니다.  
  
     [!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]
     [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]  
  
### CodeDOM 그래프에서 코드를 생성하려면  
  
-   <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 메서드를 호출하여 CodeDOM 그래프에서 소스 코드를 생성합니다.  
  
     [!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]
     [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]  
  
### 그래프를 만들고 코드를 생성하려면  
  
1.  앞 단계에서 만든 메서드를 첫 번째 단계에서 정의한 `Main` 메서드에 추가합니다.  
  
     [!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]
     [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]  
  
2.  생성하는 클래스를 컴파일하여 실행합니다.  
  
## 예제  
 다음 코드 예제에서는 위의 단계에서 생성된 코드를 보여 줍니다.  
  
 [!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)]
 [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]  
  
 이 예제를 컴파일하여 실행하면 다음 소스 코드가 생성됩니다.  
  
 [!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)]
 [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]  
  
 생성된 소스 코드를 컴파일하여 실행하면 다음 출력이 생성됩니다.  
  
```  
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## 코드 컴파일  
  
-   이 코드 예제를 실행하려면 `FullTrust` 권한 집합이 필요합니다.  
  
## 참고 항목  
 [CodeDOM 사용](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)   
 [CodeDOM 그래프에서 소스 코드 생성 및 컴파일](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)