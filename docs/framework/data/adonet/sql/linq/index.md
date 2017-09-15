---
title: LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
caps.latest.revision: 4
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3c6410d06565c9dcb9696d0fcb4f3fc749a19c48
ms.contentlocale: ko-kr
ms.lasthandoff: 09/05/2017

---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 관계형 데이터를 개체로 관리하는 데 필요한 런타임 인프라를 제공하는 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 버전 3.5의 구성 요소입니다.  
  
> [!NOTE]
>  관계형 데이터는 테이블 간에 서로 관계된 공통 열이 있는 이차원 테이블(*관계* 또는 *플랫 파일*)의 컬렉션으로 표시됩니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 효율적으로 사용하려면 관계형 데이터베이스의 기본 원리에 대해 조금은 알고 있어야 합니다.  
  
 
          [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 관계형 데이터베이스의 데이터 모델은 개발자의 프로그래밍 언어로 표현되는 개체 모델에 매핑됩니다. 응용 프로그램을 실행하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 개체 모델의 SQL 언어 통합 쿼리를 변환하여 실행을 위해 데이터베이스로 전송합니다. 데이터베이스에서 결과를 반환하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 해당 결과를 사용자의 프로그래밍 언어로 작업할 수 있는 개체로 다시 변환합니다.  
  
 일반적으로 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]의 많은 기능을 구현하는 데 필요한 사용자 인터페이스를 제공하는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]를 사용합니다.  
  
 이 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 릴리스에 포함된 설명서에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램을 빌드하는 데 필요한 기본 빌드 블록, 프로세스 및 기술에 대해 설명합니다. 또한 MSDN 라이브러리에서 특정 문제를 검색할 수 있으며 전문가와 함께 더욱 심화된 주제를 자세히 논의할 수 있는 [LINQ 포럼](http://go.microsoft.com/fwlink/?LinkId=76488)에 참여할 수 있습니다. 마지막으로 [LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205)(LINQ to SQL: 관계형 데이터에 대한 .NET Language-Integrated Query) 백서에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 및 C# 코드 예제를 통해 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술에 대해 자세히 설명합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [시작](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 방법에 대한 정보와 함께 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대한 간략한 개요를 제공합니다.  
  
 [프로그래밍 가이드](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 매핑, 쿼리, 업데이트, 디버깅 및 유사한 작업에 대한 단계를 제공합니다.  
  
 [참조](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 일부 측면에 대한 참조 정보를 제공합니다. 항목에는 SQL-CLR 형식 매핑, 표준 쿼리 연산자 변환 등이 포함됩니다.  
  
 [샘플](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 및 C# 샘플에 대한 링크를 제공합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [LINQ(Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 기술에 대한 개요를 제공합니다.  
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 사용자를 위해 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 기술에 대해 설명합니다.  
  
 [LINQ to ADO.NET](http://msdn.microsoft.com/en-us/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 포털에 대한 링크입니다.  
  
 [LINQ to SQL 연습](http://msdn.microsoft.com/en-us/308e66ac-f704-4e00-9b4e-7af0045a2374)  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대한 연습을 제공합니다.  
  
 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 설명서에 사용되는 샘플 데이터베이스를 다운로드하는 방법에 대해 설명합니다.  
  
 [LinqDataSource 기술 개요](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136)  
 <xref:System.Web.UI.WebControls.LinqDataSource> 컨트롤에서 [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] 데이터 소스 컨트롤 아키텍처를 통해 [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)]를 웹 개발자에게 노출시키는 방법에 대해 설명합니다.

