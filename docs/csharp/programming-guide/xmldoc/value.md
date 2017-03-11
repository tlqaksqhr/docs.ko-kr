---
title: "&lt;value&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<value>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<value> C# XML 태그"
  - "value C# XML 태그"
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# &lt;value&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<value>property-description</value>  
```  
  
#### 매개 변수  
 `property-description`  
 속성에 대한 설명입니다.  
  
## 설명  
 \<value\> 태그를 사용하여 속성이 나타내는 값을 설명할 수 있습니다.  Visual Studio .NET 개발 환경의 코드 마법사를 통해 속성을 추가하면 새 속성에 대한  [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md) 태그도 추가됩니다.  그러면 사용자는 직접 \<value\> 태그를 추가하여 속성이 나타내는 값을 설명해야 합니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 [!code-cs[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/value_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)