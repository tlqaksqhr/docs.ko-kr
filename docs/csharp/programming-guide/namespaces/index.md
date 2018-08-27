---
title: 네임스페이스(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 60e4c6e98ca9e71d1a095a0c7ee1df6be6d13f4b
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934875"
---
# <a name="namespaces-c-programming-guide"></a>네임스페이스(C# 프로그래밍 가이드)
네임스페이스는 C# 프로그래밍에서 두 가지 방법으로 많이 사용됩니다. 첫째, .NET Framework는 네임스페이스를 사용하여 다음과 같이 많은 클래스를 구성합니다.  
  
 [!code-csharp[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 `System`은 네임스페이스이고 `Console`은 해당 네임스페이스의 클래스입니다. 전체 키워드가 필요하지 않으므로 다음 예처럼 `using` 키워드를 사용할 수 있습니다.  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-csharp[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 자세한 내용은 [using 지시문](../../../csharp/language-reference/keywords/using-directive.md)을 참조하세요.  
  
 둘째, 고유한 네임스페이스를 선언하면 대규모 프로그래밍 프로젝트에서 클래스 및 메서드 이름의 범위를 제어할 수 있습니다. 다음 예와 같이 [네임스페이스](../../../csharp/language-reference/keywords/namespace.md) 키워드를 사용하여 네임스페이스를 선언합니다.  
  
 [!code-csharp[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## <a name="namespaces-overview"></a>네임스페이스 개요  
 네임스페이스에는 다음과 같은 속성이 있습니다.  
  
-   대규모 코드 프로젝트를 구성합니다.  
  
-   `.` 연산자를 사용하여 구분됩니다.  
  
-   `using directive`는 모든 클래스에 대해 네임스페이스의 이름을 지정할 필요가 없습니다.  
  
-   `global` 네임스페이스는 "루트" 네임스페이스입니다. `global::System`은 항상 .NET Framework 네임스페이스 `System`을 참조합니다.  
  
## <a name="related-sections"></a>관련 단원  
 네임스페이스에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [네임스페이스 사용](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [방법: 전역 네임스페이스 별칭 사용](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [방법: My 네임스페이스 사용](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [네임스페이스 키워드](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [using 지시문](../../../csharp/language-reference/keywords/using-directive.md)  
 [:: 연산자](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [. 연산자](../../../csharp/language-reference/operators/member-access-operator.md)
