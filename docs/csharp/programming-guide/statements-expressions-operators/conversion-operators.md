---
title: "변환 연산자(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 056971dcd648208d77573c180df28ffdd46788c5
ms.sourcegitcommit: 22a48b64a0150a60b00b4fc4d8c62cde7f1670c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2018
---
# <a name="conversion-operators-c-programming-guide"></a>변환 연산자(C# 프로그래밍 가이드)
C#을 사용하면 프로그래머가 클래스 또는 구조체를 다른 클래스 또는 구조체나 기본 형식으로/에서 변환할 수 있도록 클래스 또는 구조체에서 변환을 선언할 수 있습니다. 변환은 연산자처럼 정의되며 변환 결과의 형식에 따라 이름이 지정됩니다. 변환할 인수의 형식이나 변환 결과의 형식 중 하나만 포함 형식이어야 하며 둘 다 포함 형식이면 안 됩니다.  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a>변환 연산자 개요  
 변환 연산자에는 다음과 같은 속성이 있습니다.  
  
-   `implicit`로 선언된 변환은 필요한 경우 자동으로 발생합니다.  
  
-   `explicit`로 선언된 변환은 캐스트를 호출해야 합니다.  
  
-   모든 변환은 `static`으로 선언되어야 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 추가 정보  
  
-   [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [캐스팅 및 형식 변환](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [방법: 구조체 간의 사용자 정의 변환 구현](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [explicit](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [implicit](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [static](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Convert>  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)(C#의 연결된 사용자 정의 명시적 변환)
