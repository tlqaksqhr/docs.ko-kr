---
title: "#region(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#region"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#region 지시문[C#]"
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# #region(C# 참조)
`#region`을 사용하면 Visual Studio 코드 편집기의 [개요 표시 및 숨기기](/visual-studio/ide/outlining) 기능으로 확장하거나 축소할 수 있는 코드 블록을 지정할 수 있습니다.  더 긴 코드 파일에서는 현재 작업 중인 파일 부분에 초점을 맞출 수 있도록 하나 이상의 영역을 축소하거나 숨길 수 있으면 편리합니다.  다음 예제에서는 영역을 정의하는 방법을 보여 줍니다.  
  
```  
  
      #region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## 설명  
 `#region` 블록은 [\#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) 지시문으로 종료해야 합니다.  
  
 `#region` 블록은 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 블록과 겹칠 수 없습니다.  그러나 `#if` 블록 안에 `#region` 블록을 중첩시키거나 `#region` 블록 안에 `#if` 블록을 중첩시킬 수는 있습니다.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)