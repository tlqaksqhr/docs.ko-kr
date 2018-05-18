---
title: '방법: 두 인터페이스의 멤버를 명시적으로 구현(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [C#], explicitly implementing interface members
- interfaces [C#], explicitly implementing with inheritance
ms.assetid: 8b402ddc-dff9-4869-89cb-d718c764e68e
ms.openlocfilehash: c73089fdbf1350c1aff68ac3e8e78be00e21b931
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-explicitly-implement-members-of-two-interfaces-c-programming-guide"></a>방법: 두 인터페이스의 멤버를 명시적으로 구현(C# 프로그래밍 가이드)
명시적 [인터페이스](../../../csharp/language-reference/keywords/interface.md) 구현을 통해 프로그래머는 멤버 이름이 같고 각 인터페이스 멤버에 별도 구현을 제공하는 두 인터페이스를 구현할 수도 있습니다. 이 예제에서는 미터 단위와 인치 단위 모두로 상자 크기를 표시합니다. 상자 [class](../../../csharp/language-reference/keywords/class.md)는 서로 다른 측정 시스템을 나타내는 두 인터페이스 IEnglishDimensions 및 IMetricDimensions를 구현합니다. 두 인터페이스에 동일한 멤버 이름 Length와 Width가 있습니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csProgGuideInheritance#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_1.cs)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 기본 측정값을 인치 단위로 설정하려면 일반적으로 Length 및 Width 메서드를 구현하고, IMetricDimensions 인터페이스에서 Length 및 Width 메서드를 명시적으로 구현합니다.  
  
 [!code-csharp[csProgGuideInheritance#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_2.cs)]  
  
 이 경우 클래스 인스턴스에서 인치 단위에 액세스하고 인터페이스 인스턴스에서 미터 단위에 액세스할 수 있습니다.  
  
 [!code-csharp[csProgGuideInheritance#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-members-of-two-interfaces_3.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [클래스 및 구조체](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [인터페이스](../../../csharp/programming-guide/interfaces/index.md)  
 [방법: 인터페이스 멤버를 명시적으로 구현](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-interface-members.md)
