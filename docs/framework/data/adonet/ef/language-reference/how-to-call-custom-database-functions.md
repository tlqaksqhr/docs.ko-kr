---
title: "방법: 사용자 지정 데이터베이스 함수 호출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3d3f2e0235c5e141673d0b3f51c85e5e51e86694
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-call-custom-database-functions"></a>방법: 사용자 지정 데이터베이스 함수 호출
이 항목에서는 LINQ to Entities 쿼리 내에서 데이터베이스에 정의된 사용자 지정 함수를 호출하는 방법에 대해 설명합니다.  
  
 LINQ to Entities 쿼리에서 호출된 데이터베이스 함수는 데이터베이스에서 실행됩니다. 데이터베이스에서 함수를 실행하면 응용 프로그램 성능이 향상될 수 있습니다.  
  
 다음 절차에서는 사용자 지정 데이터베이스 함수를 호출하는 방법에 대해 간단히 설명합니다. 절차 다음에 나오는 예제에서는 절차의 단계를 보다 자세히 설명합니다.  
  
### <a name="to-call-custom-functions-that-are-defined-in-the-database"></a>데이터베이스에 정의되어 있는 사용자 지정 함수를 호출하려면  
  
1.  데이터베이스에서 사용자 지정 함수를 만듭니다.  
  
     SQL Server에서 사용자 지정 함수를 만드는 방법에 대 한 자세한 내용은 참조 [CREATE FUNCTION (TRANSACT-SQL)](http://go.microsoft.com/fwlink/?LinkID=139871)합니다.  
  
2.  .edmx 파일의 SSDL(저장소 스키마 정의 언어)에서 함수를 선언합니다. 함수의 이름은 데이터베이스에 선언된 함수의 이름과 같아야 합니다.  
  
     자세한 내용은 참조 [함수 요소 (SSDL)](http://msdn.microsoft.com/en-us/b60cfc3d-8b93-423e-8c99-b867256640a4)합니다.  
  
3.  해당되는 메서드를 응용 프로그램 코드의 클래스에 추가하고 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 메서드에 적용합니다. 특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> 매개 변수는 개념적 모델의 네임스페이스 이름이고, 특성의 <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> 매개 변수는 개념적 모델의 함수 이름입니다. LINQ에서 함수 이름을 확인할 때는 대/소문자가 구분됩니다.  
  
4.  LINQ to Entities 쿼리에서 메서드를 호출합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 LINQ to Entities 쿼리 내에서 사용자 지정 데이터베이스 함수를 호출하는 방법에 대해 설명합니다. 이 예제에서는 School 모델을 사용합니다. School 모델에 대 한 정보를 참조 하십시오. [School 예제 데이터베이스를 만드는](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) 및 [학교.edmx 파일을 생성](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758)합니다.  
  
 다음 코드에서는 `AvgStudentGrade` 함수를 School 샘플 데이터베이스에 추가합니다.  
  
> [!NOTE]
>  사용자 지정 데이터베이스 함수를 호출하는 단계는 데이터베이스 서버에 상관없이 동일합니다. 그러나 아래의 코드는 SQL Server 데이터베이스에서 함수를 만드는 작업과 관련된 것입니다. 다른 데이터베이스 서버에서 사용자 지정 함수를 만드는 작업에 대한 코드는 다를 수 있습니다.  
  
 [!code-sql[DP L2E MapToDBFunction#1](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]  
  
## <a name="example"></a>예  
 다음으로 .edmx 파일의 SSDL(저장소 스키마 정의 언어)에서 함수를 선언합니다. 다음 코드에서는 SSDL에서 `AvgStudentGrade` 함수를 선언합니다.  
  
 [!code-xml[DP L2E MapToDBFunction#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]  
  
## <a name="example"></a>예  
 이제 메서드를 만들고 해당 메서드를 SSDL에서 선언된 함수로 매핑합니다. <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>를 사용하여 다음 클래스의 메서드가 위의 SSDL에서 정의된 함수로 매핑됩니다. 이 메서드가 호출되면 데이터베이스에 있는 해당되는 함수가 실행됩니다.  
  
 [!code-csharp[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
 [!code-vb[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]  
  
## <a name="example"></a>예  
 마지막으로 LINQ to Entities 쿼리에서 메서드를 호출합니다. 다음 코드에서는 학생의 성 및 평균 학점을 콘솔에 표시합니다.  
  
 [!code-csharp[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
 [!code-vb[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]  
  
## <a name="see-also"></a>참고 항목  
 [.edmx 파일 개요](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [LINQ to Entities에서 쿼리](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
