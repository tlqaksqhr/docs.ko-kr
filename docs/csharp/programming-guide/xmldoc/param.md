---
title: "&lt;param&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "param"
  - "<param>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<param> C# XML 태그"
  - "param C# XML 태그"
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# &lt;param&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<param name="name">description</param>  
```  
  
#### 매개 변수  
 `name`  
 메서드 매개 변수의 이름입니다.  name은 큰따옴표\(" "\)로 묶습니다.  
  
 `description`  
 매개 변수에 대한 설명입니다.  
  
## 설명  
 메서드의 매개 변수 중 하나를 설명하려면 메서드 선언의 주석에서 \<param\> 태그를 사용해야 합니다.  여러 매개 변수를 문서화하려면 여러 \<param\> 태그를 사용합니다.  
  
 \<param\> 태그의 텍스트는 IntelliSense, 개체 브라우저 및 코드 주석 웹 보고서에 표시됩니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 [!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/param_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)