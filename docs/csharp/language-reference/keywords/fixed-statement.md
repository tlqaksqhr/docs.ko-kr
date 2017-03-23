---
title: "fixed 문(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "fixed_CSharpKeyword"
  - "fixed"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "fixed 키워드[C#]"
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# fixed 문(C# 참조)
`fixed` 문은 가비지 수집기에서 이동 가능한 변수를 재배치할 수 없도록 합니다.  `fixed` 문은 [안전하지 않은](../../../csharp/language-reference/keywords/unsafe.md) 컨텍스트에서만 허용됩니다.  `Fixed`는 [고정 크기 버퍼](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)를 만드는 데 사용할 수도 있습니다.  
  
 `fixed` 문은 관리되는 변수에 대한 포인터를 설정하고 문 실행 중에 해당 변수를 "고정"합니다.  `fixed`가 없으면 가비지 수집 시 변수가 예기치 않게 재배치될 수 있기 때문에 이동 가능한 관리되는 변수의 포인터는 거의 사용되지 않습니다.  C\# 컴파일러에서만 `fixed` 문에 관리되는 변수에 대한 포인터를 할당할 수 있습니다.  
  
 [!code-cs[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]  
  
 배열, 문자열, 고정 크기 버퍼 또는 변수 주소를 사용하여 포인터를 초기화할 수 있습니다.  다음 예제는 변수 주소, 배열 및 문자열의 사용 방법을 보여 줍니다.  고정 크기 버퍼에 대한 자세한 내용은 [고정 크기 버퍼](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)를 참조하십시오.  
  
 [!code-cs[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]  
  
 포인터가 모두 같은 형식이라면 아래와 같이 여러 포인터를 초기화할 수 있습니다.  
  
```  
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```  
  
 서로 다른 형식의 포인터를 초기화하려면 다음 예제와 같이 `fixed` 문을 중첩하기만 하면 됩니다.  
  
 [!code-cs[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]  
  
 문의 코드가 실행된 후에는 고정된 모든 변수의 고정이 해제되어 가비지 수집 대상이 됩니다.  따라서 `fixed` 문 외부에서 이러한 변수를 참조해서는 안 됩니다.  
  
> [!NOTE]
>  fixed 문으로 초기화된 포인터는 수정할 수 없습니다.  
  
 unsafe 모드에서는 스택에 메모리를 할당할 수 있습니다. 이러한 스택은 가비지 수집의 대상이 아니므로 고정할 필요가 없습니다.  자세한 내용은 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)을 참조하십시오.  
  
## 예제  
 [!code-cs[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [고정 크기 버퍼](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)