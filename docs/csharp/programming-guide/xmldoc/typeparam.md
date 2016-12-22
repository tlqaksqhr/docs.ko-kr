---
title: "&lt;typeparam&gt;(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "typeparam"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<typeparam> C# XML 태그"
  - "typeparam C# XML 태그"
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;typeparam&gt;(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## 구문  
  
```  
<typeparam name="name">description</typeparam>  
```  
  
#### 매개 변수  
 `name`  
 형식 매개 변수의 이름입니다.  name은 큰따옴표\(" "\)로 묶습니다.  
  
 `description`  
 형식 매개 변수에 대한 설명입니다.  
  
## 설명  
 `<typeparam>` 태그는 제네릭 형식 또는 메서드 선언에 대한 주석에서 형식 매개 변수를 설명하는 데 사용됩니다.  제네릭 형식 또는 메서드의 각 형식 매개 변수에 대해 태그를 추가합니다.  
  
 자세한 내용은 [제네릭](../../../visual-basic/reference/command-line-compiler/index.md)를 참조하십시오.  
  
 `<typeparam>` 태그의 텍스트는 IntelliSense 및 [Object Browser Window](http://msdn.microsoft.com/ko-kr/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) 코드 주석 웹 보고서에 표시됩니다.  
  
 [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 [!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [문서 주석에 대한 권장 태그](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)