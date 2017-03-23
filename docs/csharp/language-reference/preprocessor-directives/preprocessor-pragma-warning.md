---
title: "#pragma warning(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#pragma warning"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#pragma warning[C#]"
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# #pragma warning(C# 참조)
`#pragma warning`은 특정 경고를 활성화하거나 비활성화하는 데 사용할 수 있습니다.  
  
## 구문  
  
```  
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### 매개 변수  
 `warning-list`  
 쉼표로 구분되는 경고 번호 목록입니다.  "CS" 접두사 없이 번호만 입력합니다.  
  
 경고 번호를 지정하지 않으면 `disable`은 모든 경고를 비활성화하고 `restore`는 모든 경고를 활성화합니다.  
  
> [!NOTE]
>  Visual Studio에서 경고 번호를 검색하려면 프로젝트를 빌드한 다음 **출력** 창에서 경고 번호를 찾아봅니다.  
  
## 예제  
  
```  
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, 3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore 3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [C\# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md)