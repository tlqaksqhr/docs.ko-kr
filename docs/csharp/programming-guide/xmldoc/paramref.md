---
title: "&lt;paramref&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "paramref"
  - "<paramref>"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<paramref> C# XML 태그"
  - "paramref C# XML 태그"
ms.assetid: 756c24c1-f591-40e8-a838-559761539b0b
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# &lt;paramref&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<paramref name="name"/>  
```  
  
#### 매개 변수  
 `name`  
 참조할 매개 변수의 이름입니다.  name은 큰따옴표\(" "\)로 묶습니다.  
  
## 설명  
 \<paramref\> 태그를 사용하면 코드 주석의 단어를 나타낼 수 있습니다. 예를 들어, \<summary\> 또는 \<remarks\> 블록에서 매개 변수를 참조할 수 있습니다.  이 단어를 굵은 글꼴이나 기울임꼴 같은 구별된 방식으로 서식 지정하도록 XML 파일을 처리할 수 있습니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 [!code-cs[csProgGuideDocComments#7](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/paramref_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)