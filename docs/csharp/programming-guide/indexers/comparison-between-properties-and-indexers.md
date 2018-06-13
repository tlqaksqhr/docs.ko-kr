---
title: 속성 및 인덱서 비교(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: a8b347be33ea6acbdf8a78a7af45fd3d0c27f8fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330374"
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a>속성 및 인덱서 비교(C# 프로그래밍 가이드)
인덱서는 속성과 비슷합니다. 다음 표에 나와 있는 차이점을 제외하면 속성 접근자에 대해 정의된 모든 규칙이 인덱서 접근자에도 적용됩니다.  
  
|속성|인덱서|  
|--------------|-------------|  
|공용 데이터 멤버인 것처럼 메서드를 호출할 수 있게 합니다.|개체 자체에 배열 표기법을 사용하여 개체의 내부 컬렉션 요소에 액세스할 수 있게 합니다.|  
|단순한 이름을 통해 액세스합니다.|인덱스를 통해 액세스합니다.|  
|정적 또는 인스턴스 멤버일 수 있습니다.|인스턴스 멤버여야 합니다.|  
|속성의 [get](../../../csharp/language-reference/keywords/get.md) 접근자에는 매개 변수가 없습니다.|인덱서의 `get` 접근자에는 인덱서와 동일한 형식 매개 변수 목록이 있습니다.|  
|속성의 [set](../../../csharp/language-reference/keywords/set.md) 접근자에는 암시적 `value` 매개 변수가 포함되어 있습니다.|인덱서의 `set` 접근자에는 인덱서와 동일한 형식 매개 변수 목록이 있으며 [value](../../../csharp/language-reference/keywords/value.md) 매개 변수도 있습니다.|  
|[자동으로 구현된 속성](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)을 사용하여 약식 구문을 지원합니다.|약식 구문을 지원하지 않습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [인덱서](../../../csharp/programming-guide/indexers/index.md)  
 [속성](../../../csharp/programming-guide/classes-and-structs/properties.md)
