---
title: "쿼리 결과를 메모리에 저장"
description: "결과 저장 방법"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 5b863961-1750-4cf9-9607-acea5054d15a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 35d908bde06ef55ba2dc93a73211f7be33b9332c
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="store-the-results-of-a-query-in-memory"></a>쿼리 결과를 메모리에 저장

쿼리는 기본적으로 데이터를 검색하고 구성하는 방법에 대한 명령 집합입니다. 쿼리는 결과의 각 후속 항목이 요청될 때 지연 실행됩니다. `foreach`를 사용하여 결과를 반복하는 경우 항목이 액세스될 때 반환됩니다. 쿼리를 평가한 후 `foreach` 루프를 실행하지 않고 결과를 저장하려면 쿼리 변수에 대해 다음 메서드 중 하나를 호출합니다.  
  
-   <xref:System.Linq.Enumerable.ToList%2A>  
  
-   <xref:System.Linq.Enumerable.ToArray%2A>  
  
-   <xref:System.Linq.Enumerable.ToDictionary%2A>  
  
-   <xref:System.Linq.Enumerable.ToLookup%2A>  
  
 쿼리 결과를 저장하는 경우 다음 예제와 같이 반환된 컬렉션 개체를 새 변수에 할당하는 것이 좋습니다.  
  
## <a name="example"></a>예제  
 [!code-cs[csProgGuideLINQ#25](../../../samples/snippets/csharp/concepts/linq/how-to-store-the-results-of-a-query-in-memory_1.cs)]  
  

## <a name="see-also"></a>참고 항목  
 [LINQ 쿼리 식](index.md)

