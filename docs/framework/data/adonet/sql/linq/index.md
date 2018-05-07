---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: 257db62fcdaba454f528c2eecedfef735291f4af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 관계형 데이터를 개체로 관리하는 데 필요한 런타임 인프라를 제공하는 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 버전 3.5의 구성 요소입니다.  
  
> [!NOTE]
>  관계형 데이터는 테이블 간에 서로 관계된 공통 열이 있는 이차원 테이블(*관계* 또는 *플랫 파일*)의 컬렉션으로 표시됩니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 효율적으로 사용하려면 관계형 데이터베이스의 기본 원리에 대해 조금은 알고 있어야 합니다.  
  
 
          [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 관계형 데이터베이스의 데이터 모델은 개발자의 프로그래밍 언어로 표현되는 개체 모델에 매핑됩니다. 응용 프로그램을 실행하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 개체 모델의 SQL 언어 통합 쿼리를 변환하여 실행을 위해 데이터베이스로 전송합니다. 데이터베이스에서 결과를 반환하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 해당 결과를 사용자의 프로그래밍 언어로 작업할 수 있는 개체로 다시 변환합니다.  
  
 사용 하 여 일반적으로 Visual Studio를 사용 하는 개발자는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], 다양 한 기능을 구현 하기 위한 사용자 인터페이스를 제공 하는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]합니다.  
  
 이 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 릴리스에 포함된 설명서에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램을 빌드하는 데 필요한 기본 빌드 블록, 프로세스 및 기술에 대해 설명합니다. 특정 문제에 대 한 Microsoft Docs를 검색할 수도 및에 참여할 수 있습니다는 [LINQ 포럼](http://go.microsoft.com/fwlink/?LinkId=76488)전문가 함께 보다 복잡 한 주제를 자세히 논의할 수 있는, 합니다. 마지막으로 [LINQ to SQL: 관계형 데이터에 대 한 쿼리.NET Language-Integrated](http://go.microsoft.com/fwlink/?LinkId=93205) 백서 세부 정보 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술, Visual Basic 및 C# 코드 예제와 함께 완료 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [시작](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 방법에 대한 정보와 함께 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대한 간략한 개요를 제공합니다.  
  
 [프로그래밍 가이드](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 매핑, 쿼리, 업데이트, 디버깅 및 유사한 작업에 대한 단계를 제공합니다.  
  
 [참조](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 일부 측면에 대한 참조 정보를 제공합니다. 항목에는 SQL-CLR 형식 매핑, 표준 쿼리 연산자 변환 등이 포함됩니다.  
  
 [샘플](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 Visual Basic 및 C# 샘플에 대 한 링크를 제공합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [LINQ(Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 기술에 대한 개요를 제공합니다.  
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 설명 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] Visual Basic 사용자를 위한 기술입니다.  
  
 [LINQ to ADO.NET](http://msdn.microsoft.com/library/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 포털에 대한 링크입니다.  
  
 [LINQ to SQL 연습](http://msdn.microsoft.com/library/308e66ac-f704-4e00-9b4e-7af0045a2374)  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대한 연습을 제공합니다.  
  
 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 설명서에 사용되는 샘플 데이터베이스를 다운로드하는 방법에 대해 설명합니다.  
  
 [LinqDataSource 기술 개요](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136)  
 <xref:System.Web.UI.WebControls.LinqDataSource> 컨트롤에서 [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] 데이터 소스 컨트롤 아키텍처를 통해 [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)]를 웹 개발자에게 노출시키는 방법에 대해 설명합니다.
