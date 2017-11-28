---
title: "방법: 포인터를 사용하여 바이트 배열 복사(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.assetid: ec16fbb4-a24e-45f5-a763-9499d3fabe0a
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 375cab76063e4c77515d6b05b42f2d97ff3efc44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a>방법: 포인터를 사용하여 바이트 배열 복사(C# 프로그래밍 가이드)
다음 예제에서는 포인터를 사용하여 배열 간에 바이트를 복사합니다.  
  
 이 예제에서는 `Copy` 메서드에서 포인터를 사용할 수 있도록 하는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 키워드를 사용합니다. [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) 문은 소스 및 대상 배열에 대한 포인터를 선언하는 데 사용됩니다. 이렇게 하면 소스 및 대상 배열의 위치가 메모리에 *고정*되므로 가비지 수집에 의해 이동되지 않습니다. `fixed` 블록이 완료되면 배열에 대한 메모리 블록이 고정 해제됩니다. 이 예제의 `Copy` 메서드는 `unsafe` 키워드를 사용하기 때문에 **/unsafe** 컴파일러 옵션으로 컴파일해야 합니다. Visual Studio에서 이 옵션을 설정하려면 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다. **빌드** 탭에서 **안전하지 않은 코드 허용**을 선택합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#18](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-use-pointers-to-copy-an-array-of-bytes_2.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [/unsafe(C# 컴파일러 옵션)](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md)  
 [가비지 수집](../../../standard/garbage-collection/index.md)
