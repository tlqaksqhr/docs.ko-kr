---
title: "&lt;list&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "list"
  - "<list>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<item> C# XML 태그"
  - "<list> C# XML 태그"
  - "<listheader> C# XML 태그"
  - "item C# XML 태그"
  - "list C# XML 태그"
  - "listheader C# XML 태그"
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# &lt;list&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### 매개 변수  
 `term`  
 `description`에서 정의할 용어입니다.  
  
 `description`  
 글머리 기호 목록이나 번호 매기기의 항목 또는 `term`의 정의입니다.  
  
## 설명  
 \<listheader\> 블록은 테이블이나 정의 목록의 머리글 행을 정의하는 데 사용됩니다.  테이블을 정의할 때는 머리글의 term에 대한 엔트리만 제공하면 됩니다.  
  
 목록의 각 항목은 \<item\> 블록으로 지정합니다.  정의 목록을 만들 때는 `term`과 `description`을 모두 지정해야 합니다.  그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록의 경우에는 `description`에 대한 입력만 제공하면 됩니다.  
  
 목록이나 테이블에 사용할 수 있는 \<item\> 블록의 수에는 제한이 없습니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 [!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/list_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)