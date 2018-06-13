---
title: 복합 키를 사용하여 조인
description: 복합 키를 사용하여 조인하는 방법입니다.
ms.date: 12/1/2016
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: e40f4d147886c07913c761bb5df83ee34d23eaba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33271216"
---
# <a name="join-by-using-composite-keys"></a>복합 키를 사용하여 조인

이 예제에서는 둘 이상의 키를 사용하여 일치를 정의하려는 조인 작업을 수행하는 방법을 보여 줍니다. 이 작업은 복합 키를 사용하여 수행됩니다. 무명 형식이나 비교할 값이 포함된 명명된 형식으로 복합 키를 만듭니다. 쿼리 변수가 메서드 경계를 넘어 전달되는 경우 키의 <xref:System.Object.Equals%2A> 및 <xref:System.Object.GetHashCode%2A>를 재정의하는 명명된 형식을 사용합니다. 속성의 이름과 속성이 나타나는 순서는 각 키에서 동일해야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 복합 키를 사용하여 세 테이블의 데이터를 조인하는 방법을 보여 줍니다.  
  
```csharp  
var query = from o in db.Orders  
    from p in db.Products  
    join d in db.OrderDetails   
        on new {o.OrderID, p.ProductID} equals new {d.OrderID,        d.ProductID} into details  
        from d in details  
        select new {o.OrderID, p.ProductID, d.UnitPrice};  
```  
  
 복합 키에 대한 형식 유추는 키에 있는 속성의 이름 및 속성이 나타나는 순서에 따라 달라집니다. 소스 시퀀스에 있는 속성에 동일한 이름이 없는 경우 키에서 새 이름을 할당해야 합니다. 예를 들어 `Orders` 테이블과 `OrderDetails` 테이블이 각각 해당 열에 다른 이름을 사용한 경우 무명 형식에서 동일한 이름을 지정하여 복합 키를 만들 수 있습니다.  
  
```csharp  
join...on new {Name = o.CustomerName, ID = o.CustID} equals   
    new {Name = d.CustName, ID = d.CustID }  
```  
  
 복합 키는 `group` 절에서도 사용할 수 있습니다.  

## <a name="see-also"></a>참고 항목  
 [LINQ 쿼리 식](index.md)  
 [join 절](../language-reference/keywords/join-clause.md)  
 [group 절](../language-reference/keywords/group-clause.md)
