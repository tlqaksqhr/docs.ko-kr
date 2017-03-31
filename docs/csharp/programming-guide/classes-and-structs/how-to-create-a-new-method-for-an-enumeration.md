---
title: "방법: 새 열거형 메서드 만들기(C# 프로그래밍 가이드) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
caps.latest.revision: 7
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
ms.openlocfilehash: 3d15cbcdd81584ea5c6ab40d231183f883a7a805
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a>방법: 새 열거형 메서드 만들기(C# 프로그래밍 가이드)
확장 메서드를 사용하여 특정 열거형 형식과 관련된 기능을 추가할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 `Grades` 열거형은 학생이 클래스에서 받을 수 있는 문자 성적을 나타냅니다. 해당 형식의 각 인스턴스가 이제 합격 성적을 나타내는지 여부를 "알 수 있도록" `Passing`이라는 확장 메서드가 `Grades` 형식에 추가됩니다.  
  
 [!code-cs[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 또한 `Extensions` 클래스에는 동적으로 업데이트되는 정적 변수가 포함되며, 확장 메서드의 반환 값이 해당 변수의 현재 값을 반영합니다. 이는 확장 메서드가 정의된 정적 클래스에서 내부적으로 직접 호출됨을 보여 줍니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 코드를 실행하려면 코드를 복사하여 [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)]에서 생성된 Visual C# 콘솔 응용 프로그램 프로젝트에 붙여넣습니다. 기본적으로 이 프로젝트는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 버전 3.5를 대상으로 하며, System.Core.dll에 대한 참조 및 System.Linq에 대한 `using` 지시문을 포함합니다. 이러한 요구 사항 중 하나 이상이 프로젝트에 없는 경우 수동으로 추가할 수 있습니다.   
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [확장명 메서드](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
