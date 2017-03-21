---
title: "방법: 식 트리를 사용 하 여 동적 쿼리 (Visual Basic) 빌드 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 8d69be78a9f3568535dffe54e21af80c6eb12f70
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-expression-trees-to-build-dynamic-queries-visual-basic"></a>방법: 식 트리를 사용 하 여 동적 쿼리 (Visual Basic) 빌드
Linq에서는 식 트리는 소스를 나타내는 구조화 된 쿼리를 해당 대상 <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> 를 구현 하는 데이터의 사용 예를 들어, LINQ 공급자 구현에서 <xref:System.Linq.IQueryable%601>관계형 데이터 저장소를 쿼리 하기 위한 인터페이스입니다.</xref:System.Linq.IQueryable%601> Visual Basic 컴파일러는 런타임에 식 트리를 작성 하는 코드에 이러한 데이터 소스를 대상으로 하는 쿼리를 컴파일합니다. 그런 다음 쿼리 공급자 식 트리 데이터 구조를 탐색 하 고 데이터 원본에 대 한 적절 한 쿼리 언어로 변환할 수 있습니다.  
  
 <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601> 형식의 변수에 할당 된 람다 식을 나타내는 데 LINQ 식 트리는 또한 사용  
  
 이 항목에서는 동적 LINQ 쿼리를 만드는 식 트리를 사용 하는 방법에 설명 합니다. 동적 쿼리는 컴파일 시 쿼리의 세부 사항을 알 수 없는 경우에 유용 합니다. 예를 들어, 응용 프로그램은 최종 사용자는 데이터를 필터링 하는 하나 이상의 조건자를 지정할 수 있게 하는 사용자 인터페이스를 제공할 수 있습니다. LINQ 쿼리를 사용 하려면 이러한 유형의 응용 프로그램에서 런타임에 LINQ 쿼리를 만드는 식 트리를 사용 해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 식 트리 생성에 대 한 쿼리를 사용 하는 방법을 보여 줍니다.는 `IQueryable` 데이터 소스를 실행 합니다. 코드는 다음 쿼리를 나타내는 식 트리를 작성 합니다.  
  
 `companies.Where(Function(company) company.ToLower() = "coho winery" OrElse company.Length > 16).OrderBy(Function(company) company)`  
  
 팩터리 메서드는 <xref:System.Linq.Expressions>네임 스페이스는 전체 쿼리를 구성 하는 식을 나타내는 식 트리를 만드는 데 사용 됩니다.</xref:System.Linq.Expressions> 표준 쿼리 연산자 메서드 호출을 나타내는 식 참조는 <xref:System.Linq.Queryable>이러한 메서드의 구현입니다.</xref:System.Linq.Queryable> 최종 식 트리가 전달 되는 <xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29>의 공급자 구현에서 `IQueryable` 형식의 실행 가능한 쿼리를 만들 때 데이터 원본 `IQueryable`.</xref:System.Linq.IQueryProvider.CreateQuery%60%601%28System.Linq.Expressions.Expression%29> 결과 해당 쿼리 변수를 열거 하 여 가져옵니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 이 코드는 고정된 된 수의 식에 전달 되는 조건자에 사용 하 여는 `Queryable.Where` 메서드. 그러나 사용자 입력에 의존 하는 조건자 식의 변수 숫자를 결합 하는 응용 프로그램을 작성할 수 있습니다. 사용자의 입력에 따라 쿼리에서 호출 된 표준 쿼리 연산자를 변경할 수 있습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   새 **콘솔 응용 프로그램** 프로젝트입니다.  
  
-   아직 참조 하지 않는 경우 System.Core.dll에 대 한 참조를 추가 합니다.  
  
-   System.Linq.Expressions 네임 스페이스를 포함 합니다.  
  
-   이 예제에서 코드를 복사 하 고 붙여 넣습니다는 `Main` `Sub` 프로시저입니다.  
  
## <a name="see-also"></a>참고 항목  
 [식 트리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)   
 [방법: 식 트리 (Visual Basic)를 실행 합니다.](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
