---
title: "고정 크기 버퍼(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: 31
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e1a3dcf953cb56fc3436fdd5e7ecb60478a12922
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="fixed-size-buffers-c-programming-guide"></a>고정 크기 버퍼(C# 프로그래밍 가이드)
C#에서는 [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) 문을 사용하여 데이터 구조에 고정 크기 배열이 있는 버퍼를 만들 수 있습니다. 그러면 다른 언어로 작성된 코드 같은 기존 코드, 기존 DLL 또는 COM 프로젝트로 작업할 때 유용합니다. 고정 배열은 일반 구조체 멤버에 허용되는 특성이나 한정자를 사용할 수 있습니다. 배열 형식이 `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` 또는 `double`이어야 한다는 것이 유일한 제한 사항입니다.  
  
```  
private fixed char name[30];  
```  
  
## <a name="remarks"></a>주의  
 초기 C# 버전에서는 배열이 포함된 C# 구조체에 배열 요소가 포함되어 있지 않기 때문에 C++ 스타일 고정 크기 구조체를 선언하기가 어려웠습니다. 대신 구조체에 요소에 대한 참조가 포함되어 있습니다.  
  
 C# 2.0에서는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 코드 블록에서 사용될 경우 [struct](../../../csharp/language-reference/keywords/struct.md)에 고정 크기 배열을 포함하는 기능을 추가했습니다.  
  
 예를 들어 C# 2.0 이전에는 다음 `struct`의 크기가 8바이트입니다. `pathName` 배열은 힙 할당 배열에 대한 참조입니다.  
  
 [!code-cs[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]  
  
 C# 2.0부터는 `struct`에 포함된 배열이 포함될 수 있습니다. 다음 예제에서 `fixedBuffer` 배열은 고정 크기입니다. 배열의 요소에 액세스하려면 `fixed` 문을 사용하여 첫 번째 요소에 대한 포인터를 설정합니다. `fixed` 문은 `fixedBuffer`의 인스턴스를 메모리의 특정 위치에 고정합니다.  
  
 [!code-cs[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]  
  
 128개 요소 `char` 배열의 크기는 256바이트입니다. 고정 크기 [char](../../../csharp/language-reference/keywords/char.md) 버퍼는 인코딩에 관계없이 항상 문자당 2바이트를 사용합니다. 이는 char 버퍼가 `CharSet = CharSet.Auto` 또는 `CharSet = CharSet.Ansi`를 사용하는 API 메서드 또는 구조체로 마샬링되는 경우에도 마찬가지입니다. 자세한 내용은 <xref:System.Runtime.InteropServices.CharSet>을 참조하십시오.  
  
 또 다른 일반적인 고정 크기 배열은 [bool](../../../csharp/language-reference/keywords/bool.md) 배열입니다. `bool` 배열의 요소 크기는 항상 1바이트입니다. `bool` 배열은 비트 배열이나 버퍼를 만드는 데 적합하지 않습니다.  
  
> [!NOTE]
>  [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)를 사용하여 만든 메모리를 제외하고 C# 컴파일러와 CLR(공용 언어 런타임)에서 보안 버퍼 오버런 검사를 수행하지 않습니다. 모든 안전하지 않은 코드와 마찬가지로 주의해야 합니다.  
  
 안전하지 않은 버퍼는 다음과 같은 측면에서 일반 배열과 다릅니다.  
  
-   안전하지 않은 버퍼는 안전하지 않은 컨텍스트에서만 사용할 수 있습니다.  
  
-   안전하지 않은 버퍼는 항상 벡터 또는 1차원 배열입니다.  
  
-   배열의 선언에는 `char id[8]`와 같이 개수가 포함되어야 합니다. `char id[]`를 대신 사용할 수 없습니다.  
  
-   안전하지 않은 버퍼는 안전하지 않은 컨텍스트에서 구조체의 인스턴스 필드만 될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [상호 운용성](../../../csharp/programming-guide/interop/index.md)

