---
title: "/doc (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FileProperties.BuildAction"
  - "/doc"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "comments, C# code"
  - "XML documentation [C#], comments in source files"
  - "doc compiler option [C#]"
  - "Visual C#, XML documentation for"
  - "-doc compiler option [C#]"
  - "/doc compiler option [C#]"
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /doc (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

**\/doc** 옵션을 사용하면 XML 파일에 문서 주석을 포함시킬 수 있습니다.  
  
## 구문  
  
```  
/doc:file  
```  
  
## 인수  
 `file`  
 컴파일에 사용되는 소스 코드 파일에 주석을 표시하는 XML의 출력 파일입니다.  
  
## 설명  
 소스 코드 파일에서 다음 항목 앞에 나오는 문서 주석을 처리하여 XML 파일에 추가할 수 있습니다.  
  
-   [클래스](../../../csharp/language-reference/keywords/class.md), [delegate](../../../csharp/language-reference/keywords/delegate.md) 또는 [인터페이스](../../../csharp/language-reference/keywords/interface.md) 등의 사용자 정의 형식  
  
-   필드, [이벤트](../../../csharp/language-reference/keywords/event.md), [속성](../../../csharp/programming-guide/classes-and-structs/using-properties.md) 또는 메서드 등의 멤버  
  
 Main을 포함하는 소스 코드 파일은 먼저 XML로 출력됩니다.  
  
 생성된 .xml 파일을 [IntelliSense](/visual-studio/ide/using-intellisense) 기능과 함께 사용하려면, .xml 파일의 파일 이름을 지원하려는 어셈블리와 같도록 설정한 다음 해당 .xml 파일을 어셈블리와 같은 디렉터리에 넣습니다.  따라서 Visual Studio 프로젝트에서 이 어셈블리가 참조되는 경우에는 해당 .xml 파일도 함께 찾습니다.  자세한 내용은 [코드 주석 제공](/visual-studio/ide/supplying-xml-code-comments)을 참조하십시오.  
  
 만약 [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)을 사용하여 컴파일하지 않으면, `file` 은 컴파일의 출력의 어셈블리 매니페스트를 포함하는 파일의 이름을 지정하는 \<어셈블리\>\<\/어셈블리\>태그를 포함합니다.  
  
> [!NOTE]
>  \/doc 옵션은 모든 입력 파일에 적용되며, 프로젝트 설정에 지정하면 프로젝트의 모든 파일에 적용됩니다.  특정 파일 또는 코드 섹션에서 문서 주석과 관련된 경고를 비활성화하려면[\#pragma warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md)을 사용합니다.  
  
 코드 주석에서 문서를 생성하는 방법에 대한 자세한 내용은 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성** 페이지를 엽니다.  
  
2.  **빌드** 탭을 클릭합니다.  
  
3.  **XML 문서 파일** 속성을 수정합니다.  
  
 이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>을 참조하십시오.  
  
## 참고 항목  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)