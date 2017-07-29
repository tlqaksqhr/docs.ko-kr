---
title: "개체의 컬렉션 쿼리"
description: "컬렉션 쿼리 방법입니다."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 87a76f8a-0b58-4791-90ea-2fe0a30416c9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e08f2e5877ffe24f5a238ab19abb9760cb442f2
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="query-a-collection-of-objects"></a>개체의 컬렉션 쿼리
다음 예제는 `Student` 개체의 목록에 대해 간단한 쿼리를 수행하는 방법을 보여 줍니다. 각 `Student` 개체에는 학생에 대한 몇 가지 기본 정보와 네 개 시험에서 학생의 점수를 나타내는 목록이 있습니다.  
  
 이 응용 프로그램은 이 섹션에서 동일한 `students` 데이터 소스를 사용하는 많은 다른 예제의 프레임워크 역할을 합니다.  
  
## <a name="example"></a>예제  
 다음 쿼리는 첫 번째 시험에서 90점 이상의 점수를 받은 학생을 반환합니다.  
  
 [!code-cs[csProgGuideLINQ#15](../../../samples/snippets/csharp/concepts/linq/how-to-query-a-collection-of-objects_1.cs)]  
  
 이 쿼리는 사용자가 실험할 수 있도록 의도적으로 간단하게 만든 쿼리입니다. 예를 들어, `where` 절에서 더 많은 조건을 시도하거나 `orderby` 절을 사용하여 결과를 정렬할 수 있습니다.  
  

## <a name="see-also"></a>참고 항목  
 [LINQ 쿼리 식](index.md)

