---
title: "중첩 그룹 만들기"
description: "중첩 그룹을 만드는 방법입니다."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 232aa46d975d7c338bbc776e3867f2e566601fde
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="create-a-nested-group"></a>중첩 그룹 만들기

다음 예제에서는 LINQ 쿼리 식에서 중첩 그룹을 만드는 방법을 보여 줍니다. 학년 또는 성적 수준에 따라 만들어진 각 그룹은 개인의 이름에 따라 하위 그룹으로 추가로 구분됩니다.  
  
## <a name="example"></a>예제

 > [!NOTE]
 > 이 예제에는 [개체의 컬렉션 쿼리](query-a-collection-of-objects.md)에서 샘플 코드에 정의된 개체에 대한 참조가 포함됩니다. 

 [!code-csharp[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]  
  
 중첩 그룹의 내부 요소를 반복하려면 세 개의 중첩 `foreach` 루프가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ 쿼리 식](index.md)
