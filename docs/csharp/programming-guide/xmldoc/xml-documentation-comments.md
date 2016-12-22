---
title: "XML 문서 주석(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "cs.xml"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, XML 코드 주석"
  - "C# 소스 코드 파일"
  - "주석[C#], XML"
  - "문서 주석[C#]"
  - "XML[C#], 코드 주석"
  - "XML 문서 주석[C#]"
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
caps.latest.revision: 26
caps.handback.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# XML 문서 주석(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Visual C\#에서는 주석이 참조하는 코드 블록 바로 앞의 소스 코드의 특별 주석 필드\(세 개의 슬래시로 표시\)에 XML 요소를 포함하여 코드에 대한 문서를 만들 수 있습니다. 예를 들면 다음과 같습니다.  
  
```  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass{}  
```  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 옵션을 사용하여 컴파일하는 경우 컴파일러는 소스 코드에서 모든 XML 태그를 검색하고 XML 문서 파일을 만듭니다.  컴파일러에서 생성한 파일을 기반으로 최종 문서를 만들려면 사용자 지정 도구를 만들거나 [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061)과 같은 도구를 사용하면 됩니다.  
  
 XML 요소를 참조하려면\(예를 들어, 함수가 XML 문서 주석에서 설명하려는 특정 XML 요소를 처리하는 경우\) 표준 인용 메커니즘\(`<` 및 `>`\)을 사용할 수 있습니다.  코드 참조\(`cref`\) 요소에서 제네릭 식별자를 참조하려면 이스케이프 문자\(예: `cref=”List<T>”`\) 또는 괄호\(`cref=”List{T}”`\)를 사용할 수 있습니다.  특별한 경우로, 컴파일러는 제네릭 식별자를 참조할 때 문서 주석을 더 쉽게 작성할 수 있도록 괄호를 꺾쇠 괄호로 구문 분석합니다.  
  
> [!NOTE]
>  XML 문서 주석은 메타데이터가 아닙니다. 이러한 주석은 컴파일된 어셈블리에 포함되지 않으므로 리플렉션을 통해 액세스할 수 없습니다.  
  
## 단원 내용  
  
-   [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [XML 파일 처리](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [문서 태그에 대한 구분 기호](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [방법: XML 문서 기능 사용](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## 관련 단원  
 자세한 내용은 다음을 참조하십시오.  
  
-   [\/doc\(문서 주석 처리\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)