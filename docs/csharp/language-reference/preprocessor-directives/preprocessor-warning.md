---
title: "#warning(C# 참조) | Microsoft Docs"
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
  - "#warning"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#warning 지시문[C#]"
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #warning(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`#warning`을 사용하면 코드의 특정 위치에서 수준 1의 경고를 생성할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
#warning Deprecated code in this method.  
```  
  
## 설명  
 `#warning`는 일반적으로 조건부 지시문에 사용됩니다.  또한 [\#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md)로 사용자 정의 오류를 생성할 수도 있습니다.  
  
## 예제  
  
```  
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 전처리기 지시문](../../../visual-basic/reference/command-line-compiler/index.md)