---
title: LINQ to DataSet 개요
ms.date: 03/30/2017
ms.assetid: dc20a8fb-03f6-4b68-9c2b-7f7299e3070b
ms.openlocfilehash: d269ea2899ffd8005aad9912cf9273a012e13edd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765622"
---
# <a name="linq-to-dataset-overview"></a>LINQ to DataSet 개요
<xref:System.Data.DataSet>은 가장 많이 사용되는 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 구성 요소 중 하나이며 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]의 기반이 되는 연결되지 않은 프로그래밍 모델의 주요 요소이고 다양한 데이터 소스의 데이터를 명시적으로 캐시하는 데 사용할 수 있습니다. 프레젠테이션 계층의 경우 <xref:System.Data.DataSet>은 데이터 바인딩을 위해 GUI 컨트롤과 밀접하게 통합됩니다. 중간 계층의 경우 데이터의 관계 모양을 유지하는 캐시를 제공하고 빠르고 간단한 쿼리 및 계층 탐색 서비스를 포함합니다. 데이터베이스에 대한 요청 수를 줄이는 가장 일반적인 방법은 중간 계층에서 <xref:System.Data.DataSet>을 캐시 작업에 사용하는 것입니다. 예를 들어 데이터 구동 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 응용 프로그램을 가정해 봅시다. 응용 프로그램 데이터의 많은 부분은 자주 바뀌지 않으면서 세션이나 사용자를 통해 일반적으로 사용됩니다. 이 데이터를 웹 서버의 메모리에 유지하면 데이터베이스에 대한 요청의 수가 줄어서 사용자의 상호 작용 속도가 높아질 수 있습니다. 또 다른 유용한 측면에서 <xref:System.Data.DataSet> 응용 프로그램 공간으로 하나 이상의 데이터 원본에서 데이터의 하위 집합을 가져오는 데 응용 프로그램 수 있다는 점입니다. 이 경우 응용 프로그램에서는 메모리 내 데이터를 조작하는 동시에 관계 모양을 유지할 수 있습니다.  
  
 이러한 탁월함에도 불구하고 <xref:System.Data.DataSet>의 쿼리 기능에는 한계가 있습니다. <xref:System.Data.DataTable.Select%2A> 메서드는 필터링과 정렬에 사용할 수 있고 <xref:System.Data.DataRow.GetChildRows%2A> 및 <xref:System.Data.DataRow.GetParentRow%2A> 메서드는 계층 탐색에 사용할 수 있습니다. 그러나 더 복잡한 작업을 수행하려면 개발자가 사용자 지정 쿼리를 작성해야 합니다. 이 경우 응용 프로그램의 성능이 저하되고 유지 관리가 어려워질 수 있습니다.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]을 사용하면 <xref:System.Data.DataSet> 개체에 캐시된 데이터를 쉽고 빠르게 쿼리할 수 있습니다. 이러한 쿼리는 응용 프로그램 코드에 포함된 문자열 리터럴이 아니라 프로그래밍 언어 자체로 표현됩니다. 즉, 개발자가 별도의 쿼리 언어를 배우지 않아도 됩니다. 또한 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Visual Studio IDE는 컴파일 타임 구문 검사, 정적 입력 및에 대 한 IntelliSense 지원을 제공 하기 때문에 Visual Studio 개발자가 더 생산적으로 사용할 수 있도록 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]합니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]은 하나 이상의 데이터 소스에서 통합된 데이터를 쿼리하는 데도 사용할 수 있습니다. 이 기능은 데이터를 유연하게 표현하고 처리해야 하는 많은 시나리오에서 유용하게 사용할 수 있습니다. 이러한 조작 방법은 일반적인 보고, 분석 및 비즈니스 인텔리전스 응용 프로그램에 특히 필요합니다.  
  
## <a name="querying-datasets-using-linq-to-dataset"></a>LINQ to DataSet을 사용한 데이터 집합 쿼리  
 <xref:System.Data.DataSet>을 사용하여 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 개체를 쿼리하려면 먼저 <xref:System.Data.DataSet>을 채워야 합니다. 여러 가지 방법으로 데이터를 로드 하는 <xref:System.Data.DataSet>를 사용 하는 등의 <xref:System.Data.Common.DataAdapter> 클래스 또는 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)합니다. 데이터가 <xref:System.Data.DataSet> 개체에 로드되면 해당 개체를 쿼리할 수 있습니다. 으로 쿼리를 사용 하 여 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 를 사용 하 여 유사한 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] 에 대해 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]-데이터 소스를 사용 하도록 설정 합니다. [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 단일 테이블에 대해 쿼리를 수행할 수는 <xref:System.Data.DataSet> 또는 사용 하 여 둘 이상의 테이블에 대해는 <xref:System.Linq.Enumerable.Join%2A> 및 <xref:System.Linq.Enumerable.GroupJoin%2A> 표준 쿼리 연산자입니다.  
  
 [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] 쿼리는 형식화 및 형식화되지 않은 <xref:System.Data.DataSet> 개체에 대해 지원됩니다. 응용 프로그램 디자인 타임에 <xref:System.Data.DataSet> 스키마가 인식되는 경우 형식화된 <xref:System.Data.DataSet>을 사용하는 것이 좋습니다. 형식화된 <xref:System.Data.DataSet>에서 테이블과 행에는 각 열에 대한 형식화된 멤버가 있으며, 이를 통해 간단하고 이해하기 쉬운 쿼리를 만들 수 있습니다.  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]은 System.Core.dll에 구현된 표준 쿼리 연산자뿐 아니라 <xref:System.Data.DataSet> 개체 집합을 쉽게 쿼리하는 데 도움이 되는 여러 <xref:System.Data.DataRow>별 확장을 추가합니다. 이러한 <xref:System.Data.DataSet>별 확장에는 행의 시퀀스를 비교하는 연산자와 <xref:System.Data.DataRow>의 열 값에 액세스할 수 있도록 하는 메서드가 포함됩니다.  
  
## <a name="n-tier-applications-and-linq-to-dataset"></a>N 계층 응용 프로그램과 LINQ to DataSet  
 N 계층 데이터 응용 프로그램은 여러 논리 계층으로 분리된 데이터 중심 응용 프로그램입니다. 일반적인 N 계층 응용 프로그램에는 프레젠테이션 계층, 중간 계층 및 데이터 계층이 포함됩니다. 응용 프로그램 구성 요소를 별도의 계층으로 분리하면 응용 프로그램의 유지 관리성과 확장성이 높아집니다. N 계층 데이터 응용 프로그램에 대 한 자세한 내용은 참조 [n 계층 응용 프로그램에서 데이터 집합을 사용할](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20)합니다.  
  
 N 계층 응용 프로그램에서 <xref:System.Data.DataSet>은 주로 중간 계층에 사용되어 웹 응용 프로그램의 정보를 캐시합니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 쿼리 기능은 확장 메서드를 통해 구현되고 기존 ADO.NET 2.0 <xref:System.Data.DataSet>을 확장합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 집합 쿼리](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [LINQ(Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)
