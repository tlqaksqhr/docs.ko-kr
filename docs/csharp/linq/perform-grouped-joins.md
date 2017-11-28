---
title: "그룹화 조인 수행"
description: "그룹화 조인을 수행하는 방법"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.openlocfilehash: 5e26473e19a5b6107d7aceea5e9829b48aa522b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="perform-grouped-joins"></a>그룹화 조인 수행

그룹 조인은 계층적 데이터 구조를 생성하는 데 유용합니다. 첫 번째 컬렉션의 각 요소와 두 번째 컬렉션에서 상관 관계가 지정된 요소 집합을 쌍으로 구성합니다.  
  
 예를 들어 `Student`라는 클래스 또는 관계형 데이터베이스 테이블에 `Id` 및 `Name`이라는 두 개의 필드가 있을 수 있습니다. `Course`라는 두 번째 클래스 또는 관계형 데이터베이스 테이블에 `StudentId` 및 `CourseTitle`이라는 두 개의 필드가 있을 수 있습니다. 일치하는 `Student.Id` 및 `Course.StudentId`를 기반으로 하는 이러한 두 데이터 소스의 그룹 조인은 각 `Student`를 `Course` 개체 컬렉션(비어 있을 수 있음)과 그룹화합니다.  
  
> [!NOTE]
>  첫 번째 컬렉션의 각 요소는 상관 관계가 지정된 요소가 두 번째 컬렉션에 있는지 여부에 관계없이 그룹 조인의 결과 집합에 표시됩니다. 상관 관계가 지정된 요소가 없는 경우 해당 요소에 대해 상관 관계가 지정된 요소의 시퀀스가 비어 있습니다. 따라서 결과 선택기에서 첫 번째 컬렉션의 모든 요소에 액세스할 수 있습니다. 이는 두 번째 컬렉션에 일치 항목이 없는 첫 번째 컬렉션의 요소에 액세스할 수 없는 비그룹 조인의 결과 선택기와 다릅니다.  
  
 이 항목의 첫 번째 예제에서는 그룹 조인을 수행하는 방법을 보여 줍니다. 두 번째 예제에서는 그룹 조인을 사용하여 XML 요소를 만드는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
  
### <a name="group-join-example"></a>그룹 조인 예제  
 다음 예제에서는 `Pet.Owner` 속성과 일치하는 `Person`에 따라 `Person` 및 `Pet` 형식 개체의 그룹 조인을 수행합니다. 각 일치 항목에 대한 요소 쌍을 생성하는 비그룹 조인과 달리 그룹 조인은 첫 번째 컬렉션의 각 요소에 대해 하나의 결과 개체(이 예제에서는 `Person` 개체)를 생성합니다. 두 번째 컬렉션의 해당 요소(이 예제에서는 `Pet` 개체)는 컬렉션으로 그룹화됩니다. 마지막으로, 결과 선택기 함수는 `Person.FirstName` 및 `Pet` 개체 컬렉션으로 구성된 각 일치 항목에 대해 무명 형식을 만듭니다.  
  
 [!code-csharp[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]  
  
## <a name="example"></a>예제  
  
### <a name="group-join-to-create-xml-example"></a>XML을 만들기 위한 그룹 조인 예제  
 그룹 조인은 LINQ to XML을 사용하여 XML을 만드는 데 적합합니다. 다음 예제는 무명 형식을 만드는 대신 결과 선택기 함수가 조인된 개체를 나타내는 XML 요소를 만든다는 점을 제외하고 앞의 예제와 비슷합니다.  
  
 [!code-csharp[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]  
 
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq.Enumerable.Join%2A>  
 <xref:System.Linq.Enumerable.GroupJoin%2A>  
 [내부 조인 수행](perform-inner-joins.md)  
 [왼쪽 우선 외부 조인 수행](perform-left-outer-joins.md)  
 [무명 형식](../programming-guide/classes-and-structs/anonymous-types.md)  
 
