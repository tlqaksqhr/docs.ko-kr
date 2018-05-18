---
title: 인스턴스 생성자(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: 5864511e6323ca1508494abfe2350e8eaffb6a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="instance-constructors-c-programming-guide"></a>인스턴스 생성자(C# 프로그래밍 가이드)
인스턴스 생성자는 [new](../../../csharp/language-reference/keywords/new.md) 식을 사용하여 [class](../../../csharp/language-reference/keywords/class.md)의 개체를 만들 때 인스턴스 멤버 변수를 만들고 초기화하는 데 사용됩니다. [정적](../../../csharp/language-reference/keywords/static.md) 클래스 또는 비정적 클래스의 정적 변수를 초기화하려면 정적 생성자를 정의해야 합니다. 자세한 내용은 [정적 생성자](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)를 참조하세요.  
  
 다음 예제에서는 인스턴스 생성자를 보여 줍니다.  
  
 [!code-csharp[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]  
  
> [!NOTE]
>  이해를 돕기 위해 이 클래스에는 public 필드가 포함되어 있습니다. public 필드를 사용하면 어디에 있든 프로그램 내의 모든 메서드가 확인되지 않고 개체의 내부 작업에 무제한 액세스할 수 있으므로 프로그래밍 시 권장되지 않습니다. 데이터 멤버는 일반적으로 private여야 하며, 클래스 메서드 및 속성을 통해서만 액세스해야 합니다.  
  
 `CoOrds` 클래스를 기반으로 하는 개체를 만들 때마다 이 인스턴스 생성자가 호출됩니다. 인수를 사용하지 않는 이러한 생성자를 *기본 생성자*라고 합니다. 그러나 추가 생성자를 제공하는 것이 유용한 경우가 많습니다. 예를 들어 데이터 멤버에 대한 초기 값을 지정할 수 있는 생성자를 `CoOrds` 클래스에 추가할 수 있습니다.  
  
 [!code-csharp[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]  
  
 이렇게 하면 기본 또는 특정 초기 값으로 `CoOrd` 개체를 다음과 같이 만들 수 있습니다.  
  
 [!code-csharp[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]  
  
 클래스에 생성자가 없는 경우 기본 생성자가 자동으로 생성되고 개체 필드를 초기화하는 데 기본값이 사용됩니다. 예를 들어 [int](../../../csharp/language-reference/keywords/int.md)가 0으로 초기화됩니다. 기본값에 대한 자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하세요. 따라서 `CoOrds` 클래스 기본 생성자는 모든 데이터 멤버를 0으로 초기화하기 때문에 클래스의 작동 방식을 변경하지 않고 완전히 제거할 수 있습니다. 여러 생성자를 사용하는 전체 예제는 이 항목의 뒷부분에 있는 예제 1에서 제공되고, 자동으로 생성된 생성자의 예는 예제 2에서 제공됩니다.  
  
 인스턴스 생성자를 사용하여 기본 클래스의 인스턴스 생성자를 호출할 수도 있습니다. 클래스 생성자는 다음과 같이 이니셜라이저를 통해 기본 클래스의 생성자를 호출할 수 있습니다.  
  
 [!code-csharp[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]  
  
 이 예제에서 `Circle` 클래스는 `Circle`이 파생되는 `Shape`에서 제공하는 생성자에 반경과 높이를 나타내는 값을 전달합니다. `Shape` 및 `Circle`을 사용하는 전체 예제는 이 항목에서 예제 3으로 나와 있습니다.  
  
## <a name="example-1"></a>예제 1  
 다음 예제에서는 인수 없는 클래스 생성자와 두 개의 인수를 사용하는 클래스 생성자가 있는 클래스를 보여 줍니다.  
  
 [!code-csharp[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]  
  
## <a name="example-2"></a>예제 2  
 이 예제에서 `Person` 클래스에는 생성자가 없으며, 기본 생성자가 자동으로 제공되고 필드는 해당 기본값으로 초기화됩니다.  
  
 [!code-csharp[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]  
  
 `age`의 기본값은 `0`이고, `name`의 기본값은 `null`입니다. 기본값에 대한 자세한 내용은 [기본값 표](../../../csharp/language-reference/keywords/default-values-table.md)를 참조하세요.  
  
## <a name="example-3"></a>예제 3  
 다음 예제에서는 기본 클래스 이니셜라이저를 사용하는 방법을 보여 줍니다. `Circle` 클래스는 제네릭 클래스 `Shape`에서 파생되고, `Cylinder` 클래스는 `Circle` 클래스에서 파생됩니다. 각 파생 클래스의 생성자는 해당 기본 클래스 이니셜라이저를 사용합니다.  
  
 [!code-csharp[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]  
  
 기본 클래스 생성자 호출에 대한 추가 예제는 [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md), [base](../../../csharp/language-reference/keywords/base.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [생성자](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
 [static](../../../csharp/language-reference/keywords/static.md)
