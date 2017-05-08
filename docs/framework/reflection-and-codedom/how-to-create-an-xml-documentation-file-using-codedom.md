---
title: "방법: CodeDOM을 사용하여 XML 문서 파일 만들기 | Microsoft Docs"
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
  - "코드 문서 개체 모델, XML 문서 생성"
  - "CodeDOM, XML 문서 생성"
  - "XML 문서, CodeDOM을 사용하여 만들기"
ms.assetid: e3b80484-36b9-41dd-9d21-a2f9a36381dc
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: CodeDOM을 사용하여 XML 문서 파일 만들기
CodeDOM을 사용하여 XML 문서를 생성하는 코드를 만들 수 있습니다.  이 과정에는 XML 문서 주석이 들어 있는 CodeDOM 그래프를 만드는 작업, 코드를 생성하는 작업 및 XML 문서를 출력하는 컴파일러 옵션을 사용하여 생성된 코드를 컴파일하는 작업이 포함됩니다.  
  
### XML 문서 주석이 들어 있는 CodeDOM 그래프를 만들려면  
  
1.  샘플 응용 프로그램에 대해 CodeDOM 그래프가 들어 있는 <xref:System.CodeDom.CodeCompileUnit>를 만듭니다.  
  
2.  <xref:System.CodeDom.CodeCommentStatement.%23ctor%2A> 생성자를 사용하고 `docComment` 매개 변수를 `true`로 설정하여 XML 문서 주석 요소와 텍스트를 만듭니다.  
  
     [!code-csharp[CodeDomHelloWorldSample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#4)]
     [!code-vb[CodeDomHelloWorldSample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#4)]  
  
### CodeCompileUnit에서 코드를 생성하려면  
  
1.  <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 메서드를 사용하여 코드를 생성하고 컴파일할 소스 파일을 만듭니다.  
  
     [!code-csharp[CodeDomHelloWorldSample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#5)]
     [!code-vb[CodeDomHelloWorldSample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#5)]  
  
### 코드를 컴파일하고 문서 파일을 생성하려면  
  
1.  <xref:System.CodeDom.Compiler.CompilerParameters> 개체의 <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> 속성에 **\/doc** 컴파일러 옵션을 추가하고 <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> 메서드에 개체를 전달하여 코드가 컴파일될 때 XML 문서 파일을 만듭니다.  
  
     [!code-csharp[CodeDomHelloWorldSample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#6)]
     [!code-vb[CodeDomHelloWorldSample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#6)]  
  
## 예제  
 다음 코드 예제에서는 문서 주석이 있는 CodeDOM 그래프를 만들고, 그래프에서 코드 파일을 생성하고, 파일을 컴파일한 다음 관련 XML 문서 파일을 만듭니다.  
  
 [!code-csharp[CodeDomHelloWorldSample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomHelloWorldSample/cs/program.cs#1)]
 [!code-vb[CodeDomHelloWorldSample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomHelloWorldSample/vb/program.vb#1)]  
  
 이 코드 예제에서는 HelloWorldDoc.xml 파일에 다음 XML 문서를 만듭니다.  
  
```  
<?xml version="1.0" ?>   
<doc>  
  <assembly>  
    <name>HelloWorld</name>   
  </assembly>  
  <members>  
    <member name="T:Samples.Class1">  
      <summary>  
        Create a Hello World application.   
        <seealso cref="M:Samples.Class1.Main" />   
      </summary>  
    </member>  
    <member name="M:Samples.Class1.Main">  
      <summary>  
        Main method for HelloWorld application.   
        <para>Add a new paragraph to the description.</para>   
      </summary>  
    </member>  
  </members>  
</doc>  
```  
  
## 코드 컴파일  
  
-   이 코드 예제를 실행하려면 `FullTrust` 권한 집합이 필요합니다.  
  
## 참고 항목  
 [Documenting Your Code with XML](../Topic/Documenting%20Your%20Code%20with%20XML%20\(Visual%20Basic\).md)   
 [XML 문서 주석](../Topic/XML%20Documentation%20Comments%20\(C%23%20Programming%20Guide\).md)   
 [XML 문서](../Topic/XML%20Documentation%20\(Visual%20C++\).md)