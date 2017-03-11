---
title: "&lt;typeparamref&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "typeparamref"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<typeparamref> C# XML 태그"
  - "typeparamref C# XML 태그"
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# &lt;typeparamref&gt;(C# 프로그래밍 가이드)
## 구문  
  
```  
<typeparamref name="name"/>  
```  
  
#### 매개 변수  
 `name`  
 형식 매개 변수의 이름입니다.  name은 큰따옴표\(" "\)로 묶습니다.  
  
## 설명  
 제네릭 형식 및 메서드의 형식 매개 변수에 대한 자세한 내용은 [제네릭](../../../csharp/programming-guide/generics/index.md)을 참조하십시오.  
  
 이 태그를 사용하면 문서 파일의 사용자가 단어의 서식을 기울임꼴 등의 구별되는 방식으로 지정할 수 있습니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 [!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/csharp/typeparamref_1.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)