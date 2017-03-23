---
title: "&lt;example&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<example>"
  - "example"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<example> C# XML 태그"
  - "example C# XML 태그"
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# &lt;example&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<example>description</example>  
```  
  
#### 매개 변수  
 `description`  
 코드 예제에 대한 설명입니다.  
  
## 설명  
 \<example\> 태그를 사용하면 메서드나 기타 라이브러리 멤버의 사용 방법에 대한 예제를 지정할 수 있습니다.  여기에는 일반적으로 [\<code\>](../../../csharp/programming-guide/xmldoc/code.md) 태그가 함께 사용됩니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 [!code-cs[csProgGuideDocComments#3](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/example_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)