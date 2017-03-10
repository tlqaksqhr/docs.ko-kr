---
title: "&lt;remarks&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "remarks"
  - "<remarks>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<remarks> C# XML 태그"
  - "remarks C# XML 태그"
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# &lt;remarks&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<remarks>description</remarks>  
```  
  
#### 매개 변수  
 `Description`  
 멤버에 대한 설명입니다.  
  
## 설명  
 \<remarks\> 태그는 형식에 대한 정보를 추가하여 [\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md)에 지정한 정보를 보충하는 데 사용합니다.  이 정보는 [Object Browser Window](http://msdn.microsoft.com/ko-kr/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda)에 표시됩니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 [!code-cs[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/remarks_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)