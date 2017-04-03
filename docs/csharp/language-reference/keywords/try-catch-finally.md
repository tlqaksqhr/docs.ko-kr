---
title: "try-catch-finally(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
dev_langs:
- CSharp
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ebaf3d90c672bd3c069af12307f3745a12af3739
ms.lasthandoff: 03/13/2017

---
# <a name="try-catch-finally-c-reference"></a>try-catch-finally(C# 참조)
`catch` 및 `finally`를 함께 사용하는 일반적인 경우는 `try` 블록에서 리소스를 얻어 사용하고, `catch` 블록에서 예외 상황을 처리하고, `finally` 블록에서 리소스를 해제하는 것입니다.  
  
 예외를 다시 throw하는 방법에 대한 자세한 내용과 예제는 [try-catch](../../../csharp/language-reference/keywords/try-catch.md) 및 [예외 throw](https://msdn.microsoft.com/library/xhcbs8fz)를 참조하세요. `finally` 블록에 대한 자세한 내용은 [try-finally](../../../csharp/language-reference/keywords/try-finally.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 [!code-cs[csrefKeywordsExceptions#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-catch-finally_1.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [try, throw 및 catch 문(C++)](https://docs.microsoft.com/cpp/cpp/try-throw-and-catch-statements-cpp)   
 [예외 처리 문](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [방법: 명시적으로 예외 Throw](https://msdn.microsoft.com/library/xhcbs8fz)   
 [using 문](../../../csharp/language-reference/keywords/using-statement.md)
