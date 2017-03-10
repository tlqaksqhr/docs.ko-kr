---
title: "네임스페이스 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.names"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "정규화된 이름[C#]"
  - "네임스페이스[C#], 사용 방법"
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# 네임스페이스 사용(C# 프로그래밍 가이드)
네임스페이스는 C\# 프로그램에서 다음 두 가지 방식으로 중요하게 사용됩니다.  우선 .NET Framework 클래스에서는 네임스페이스를 사용하여 많은 자체 클래스를 조직화합니다.  또한 대규모 프로그래밍 프로젝트에서 클래스와 메서드 이름의 범위를 쉽게 제어할 수 있도록 고유한 네임스페이스를 정의하기도 합니다.  
  
## 네임스페이스 액세스  
 대부분의 C\# 응용 프로그램은 `using` 지시문 섹션으로 시작합니다.  이 섹션에는 응용 프로그램에서 자주 사용하는 네임스페이스가 나열됩니다. 프로그래머는 여기에 포함된 메서드를 사용할 때마다 정규화된 이름을 지정할 필요가 없습니다.  
  
 예를 들어, 다음과 같은 줄을 포함할 수 있습니다.  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/using.cs#1)]  
  
 이 경우 프로그램 시작 단계에서 다음과 같은 코드를 사용할 수 있습니다.  
  
 [!code-cs[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/progGuide.cs#31)]  
  
 using 지시문이 없으면 동일한 결과를 얻기 위해 다음 코드를 사용해야 합니다.  
  
 [!code-cs[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/progGuide.cs#30)]  
  
## 네임스페이스 별칭  
 [using 지시문](../../../csharp/language-reference/keywords/using-directive.md)을 사용하여 [네임스페이스](../../../csharp/language-reference/keywords/namespace.md)의 별칭을 만들 수도 있습니다.  예를 들어, 중첩된 네임스페이스가 들어 있는 이전에 작성된 네임스페이스를 사용하는 경우 다음 예제와 같이 특정 네임스페이스를 간단하게 참조할 수 있도록 별칭을 선언할 수 있습니다.  
  
 [!code-cs[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces2.cs#7)]  
  
## 네임스페이스를 사용하여 범위 제어  
 `namespace` 키워드는 범위를 선언하는 데 사용됩니다.  프로젝트 내에서 범위를 만들면 코드를 쉽게 구성할 수 있고 전역적으로 고유한 형식을 만들 수 있습니다.  다음 예제에서는 `SampleClass`라는 클래스를 두 네임스페이스에 정의하며, 네임스페이스 하나는 다른 네임스페이스 내에 중첩되어 있습니다.  [. 연산자](../../../csharp/language-reference/operators/member-access-operator.md)는 호출되는 메서드를 구분하는 데 사용됩니다.  
  
 [!code-cs[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#8)]  
  
## 정규화된 이름  
 네임스페이스와 형식은 고유한 이름을 갖습니다. 이 이름은 논리 계층 구조를 나타내는 정규화된 이름으로 표시됩니다.  예를 들어, `A.B` 문은 `A`가 네임스페이스나 형식의 이름이고 `B`가 그 안에 중첩되어 있음을 의미합니다.  
  
 다음 예제에는 중첩된 클래스 및 네임스페이스가 있습니다.  정규화된 이름은 각 엔터티 다음에 나오는 주석에 표시되어 있습니다.  
  
 [!code-cs[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#9)]  
  
 다음은 위 코드 세그먼트의 요소에 대한 설명입니다.  
  
-   `N1` 네임스페이스는 전역 네임스페이스의 멤버입니다.  정규화된 이름은`N1`입니다.  
  
-   `N2` 네임스페이스는 `N1`의 멤버입니다.  정규화된 이름은 `N1.N2`입니다.  
  
-   `C1` 클래스는 `N1`의 멤버입니다.  정규화된 이름은 `N1.C1`입니다.  
  
-   이 코드에서는 클래스 이름 `C2`가 두 번 사용됩니다.  그러나 정규화된 이름은 고유합니다.  `C2`의 첫 번째 인스턴스는 `C1` 내부에서 선언되므로 정규화된 이름은 `N1.C1.C2`입니다.  `C2`의 두 번째 인스턴스는 `N2` 네임스페이스 내부에서 선언되므로 정규화된 이름은 `N1.N2.C2`입니다.  
  
 위의 코드 세그먼트를 사용하여 다음과 같이 `N1.N2` 네임스페이스에 새 클래스 멤버 `C3`을 추가할 수 있습니다.  
  
 [!code-cs[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#10)]  
  
 일반적으로 `::`을 사용하여 네임스페이스 별칭을 참조하거나 `global::`을 사용하여 전역 네임스페이스를 참조하고 `.`을 사용하여 형식이나 멤버를 한정합니다.  
  
 네임스페이스 대신 형식을 참조하는 별칭과 함께 `::`을 사용하면 오류가 발생합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces2.cs#11)]  
  
 [!code-cs[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces2.cs#12)]  
  
 `global`이라는 단어는 미리 정의된 별칭이 아니라는 점에 주의해야 합니다. 따라서 `global.X`에는 특별한 의미가 없습니다.  이는 `::`과 함께 사용할 때만 특별한 의미를 갖습니다.  
  
 `global::`은 항상 전역 네임스페이스를 참조하며 별칭이 아니므로 global이라는 별칭을 정의하면 컴파일러 경고 CS0440이 발생합니다.  예를 들어, 다음과 같은 줄을 사용하면 경고가 발생합니다.  
  
 [!code-cs[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces2.cs#13)]  
  
 의도하지 않은 추가 형식이 사용되지 않도록 방지하기 위해서는 `::`을 별칭과 함께 사용하는 것이 좋습니다.  예를 들어, 다음과 같은 예제를 생각해 볼 수 있습니다.  
  
 [!code-cs[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#14)]  
  
 [!code-cs[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#15)]  
  
 이 예제는 작동은 하지만 `Alias`라는 형식을 추가로 도입하면 `Alias.`가 해당 형식에 대신 바인딩됩니다.  `Alias::Exception`을 사용하면 `Alias`가 형식으로 잘못 인식되지 않고 네임스페이스 별칭으로 취급되도록 할 수 있습니다.  
  
 `global` 별칭에 대한 자세한 내용은 [방법: 전역 네임스페이스 별칭 사용](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) 항목을 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [네임스페이스](../../../csharp/programming-guide/namespaces/index.md)   
 [네임스페이스 키워드](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [. 연산자](../../../csharp/language-reference/operators/member-access-operator.md)   
 [:: 연산자](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)