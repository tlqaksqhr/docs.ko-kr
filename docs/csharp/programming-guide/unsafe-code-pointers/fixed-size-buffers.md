---
title: "고정 크기 버퍼(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "고정 크기 버퍼[C#]"
  - "안전하지 않은 버퍼[C#]"
  - "안전하지 않은 코드[C#], 고정 크기 버퍼"
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# 고정 크기 버퍼(C# 프로그래밍 가이드)
C\#에서 [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) 문을 사용하여 데이터 구조에 배열 크기가 고정된 버퍼를 만들 수 있습니다.  고정 크기의 배열은 다른 언어로 작성된 코드와 같은 기존 코드, 기존 DLL 또는 COM 프로젝트를 사용하여 작업할 때 유용합니다.  고정 배열에는 일반 구조체 멤버에 허용되는 특성이나 한정자를 모두 사용할 수 있습니다.  유일한 제한 사항은 배열 형식이 `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` 또는 `double`이어야 한다는 점입니다.  
  
```  
private fixed char name[30];  
```  
  
## 설명  
 이전 버전의 C\#에서는 C\+\+ 스타일의 고정 크기 구조를 선언하기가 어려웠습니다. 배열을 포함하는 C\# 구조체에 배열 요소가 포함되지 않기 때문입니다.  대신, 구조체는 요소에 대한 참조를 포함합니다.  
  
 C\# 2.0에는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 코드 블록에 사용되는 [구조체](../../../csharp/language-reference/keywords/struct.md)에 고정 크기 배열을 포함할 수 있는 기능이 추가되었습니다.  
  
 예를 들어, C\# 2.0 이전에는 다음 `struct`는 8 바이트 크기가 됩니다.  `pathName` 배열은 힙에 할당된 배열 참조입니다.  
  
 [!code-cs[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#19)]  
  
 C\# 2.0부터 `struct`에 포함된 배열을 포함할 수 있습니다.  다음 예제에서는 `fixedBuffer` 배열의 크기가 고정되어 있습니다.  배열의 요소에 액세스하려면 `fixed` 문을 사용하여 첫 번째 요소에 대한 포인터를 설정합니다.  `fixed` 문은 `fixedBuffer`의 인스턴스를 메모리의 특정 위치에 고정합니다.  
  
 [!code-cs[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#20)]  
  
 128 요소 `char` 배열의 크기는 256바이트입니다.  고정 크기 [char](../../../csharp/language-reference/keywords/char.md) 버퍼에는 인코딩과 상관없이 문자 당 항상 2바이트가 사용됩니다.  이는 `CharSet = CharSet.Auto` 또는 `CharSet = CharSet.Ansi`를 사용하여 char 버퍼를 API 메서드나 구조체로 마샬링하는 경우에도 마찬가지입니다.  자세한 내용은 <xref:System.Runtime.InteropServices.CharSet>를 참조하십시오.  
  
 다른 일반적인 고정 크기 배열로는 [bool](../../../csharp/language-reference/keywords/bool.md) 배열이 있습니다.  `bool` 배열의 요소 크기는 항상 한 바이트입니다.  `bool` 배열은 비트 배열이나 버퍼를 만들기에 적절하지 않습니다.  
  
> [!NOTE]
>  [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)을 사용하여 만든 메모리를 제외하고 C\# 컴파일러와 CLR\(공용 언어 런타임\)에서는 어떠한 보안 버퍼 오버런 검사도 수행하지 않습니다.  따라서 안전하지 않은 코드와 마찬가지로 항상 주의해야 합니다.  
  
 안전하지 않은 버퍼는 다음과 같은 점에서 일반 배열과 다릅니다.  
  
-   안전하지 않은 버퍼는 안전하지 않은 컨텍스트에만 사용할 수 있습니다.  
  
-   안전하지 않은 버퍼는 항상 벡터\(1차원 배열\)입니다.  
  
-   배열 선언에는 `char id[8]` 같이 카운트가 포함되어야 합니다.  `char id[]`를 대신 사용할 수 없습니다.  
  
-   안전하지 않은 버퍼는 안전하지 않은 컨텍스트에서만 구조체의 인스턴스 필드가 될 수 있습니다.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [상호 운용성](../../../csharp/programming-guide/interop/interoperability.md)