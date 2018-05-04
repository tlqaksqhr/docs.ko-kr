---
title: 마이그레이션 고려 사항(Entity Framework)
ms.date: 03/30/2017
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
ms.openlocfilehash: ab048551f0b6ee9301e93d25257b4dfbff748af0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="migration-considerations-entity-framework"></a>마이그레이션 고려 사항(Entity Framework)
[!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] Entity Framework를 사용하면 기존 응용 프로그램보다 몇 가지 이점이 있습니다. 가장 중요한 이점 중 하나는 개념적 모델을 사용하여 응용 프로그램에서 사용되는 데이터 구조를 데이터 소스의 스키마와 구분할 수 있다는 것입니다. 이렇게 하면 응용 프로그램을 적절하게 변경하지 않아도 나중에 저장소 모델이나 데이터 소스 자체를 쉽게 변경할 수 있습니다. 사용 하 여의 이점에 대 한 자세한 내용은 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], 참조 [Entity Framework 개요](../../../../../docs/framework/data/adonet/ef/overview.md) 및 [엔터티 데이터 모델](../../../../../docs/framework/data/adonet/entity-data-model.md)합니다.  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]의 이점을 최대한 활용하기 위해 기존 응용 프로그램을 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]로 마이그레이션할 수 있습니다. 일부 작업은 마이그레이션되는 모든 응용 프로그램에 공통됩니다. 이러한 일반적인 작업에 사용 하도록 응용 프로그램을 업그레이드 포함는 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 버전 3.5 서비스 팩 1 (SP1)부터, 모델 정의 및 매핑 및 Entity Framework 구성 합니다. 응용 프로그램을 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]로 마이그레이션하는 경우 추가로 고려할 사항이 있습니다. 이러한 고려 사항은 마이그레이션되는 응용 프로그램의 종류와 응용 프로그램의 특정 기능에 따라 달라집니다. 이 항목에서는 기존 응용 프로그램을 업그레이드할 때 사용할 최상의 방법을 선택하는 데 유용한 정보를 제공합니다.  
  
## <a name="general-migration-considerations"></a>일반적인 마이그레이션 고려 사항  
 모든 응용 프로그램을 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]로 마이그레이션할 때는 다음 사항을 고려해야 합니다.  
  
-   모든 응용 프로그램을 사용 하는 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 버전 3.5 s p 1 부터는 마이그레이션하려면 Entity Framework로 응용 프로그램에서 사용 되는 데이터 원본에 대 한 데이터 공급자는 Entity Framework를 지원 하기만 합니다.  
  
-   공급자가 Entity Framework를 지원하지만 Entity Framework에서 데이터 소스 공급자의 모든 기능을 지원하지 않을 수도 있습니다.  
  
-   크거나 복잡한 응용 프로그램의 경우 한 번에 전체 응용 프로그램을 Entity Framework로 마이그레이션할 필요는 없습니다. 그러나 데이터 소스가 변경될 경우 Entity Framework를 사용하지 않는 응용 프로그램의 모든 부분을 변경해야 합니다.  
  
-   [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]는 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] 데이터 공급자를 사용하여 데이터 소스에 액세스하므로 Entity Framework에 사용되는 데이터 공급자 연결을 응용 프로그램의 다른 부분과 공유할 수 있습니다. 예를 들어, Entity Framework는 SqlClient 공급자를 사용하여 SQL Server 데이터베이스에 액세스합니다. 자세한 내용은 참조 [Entity Framework 용 EntityClient 공급자](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)합니다.  
  
## <a name="common-migration-tasks"></a>일반적인 마이그레이션 작업  
 기존 응용 프로그램을 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]로 마이그레이션하는 경로는 응용 프로그램 종류와 기존 데이터 액세스 전략에 따라 달라집니다. 그러나 기존 응용 프로그램을 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]로 마이그레이션하는 경우 항상 다음 작업을 수행해야 합니다.  
  
> [!NOTE]
>  [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)] 이상과 함께 엔터티 데이터 모델 도구를 사용하면 이러한 모든 작업이 자동으로 수행됩니다. 자세한 내용은 참조 [하는 방법: 엔터티 데이터 모델 마법사를 사용 하 여](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)합니다.  
  
1.  응용 프로그램을 업그레이드합니다.  
  
     이전 버전의 Visual Studio를 사용 하 여 만든 프로젝트 및 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 사용 하도록 업그레이드 해야 [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)] s p 1 및 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 버전 3.5 s p 1부터 시작 합니다.  
  
2.  모델 및 매핑을 정의합니다.  
  
     모델 및 매핑 파일은 개념적 모델의 엔터티, 데이터 소스의 구조(예: 테이블, 저장 프로시저 및 뷰), 엔터티와 데이터 소스 구조 간의 매핑을 정의합니다. 자세한 내용은 참조 [하는 방법: 모델 및 매핑 파일을 수동으로 정의](http://msdn.microsoft.com/library/d4fd6864-f2a1-48f0-aa32-1e318775a99a)합니다.  
  
     저장소 모델에 정의된 형식은 데이터 소스의 개체 이름과 일치해야 합니다. 기존 응용 프로그램에서 데이터를 개체로 노출하는 경우 개념적 모델에 정의된 엔터티 및 속성이 이러한 기존 데이터 클래스 및 속성의 이름과 일치하는지 확인해야 합니다. 자세한 내용은 참조 [하는 방법: 사용자 지정 모델링 및 매핑 파일 사용자 지정 개체를 사용할 수 있도록](http://msdn.microsoft.com/library/bb40c4db-0121-4e45-a167-8fb06707a708)합니다.  
  
    > [!NOTE]
    >  엔터티 데이터 모델 디자이너를 사용하여 개념적 모델의 엔터티 이름을 기존 개체와 일치하도록 바꿀 수 있습니다. 자세한 내용은 참조 [엔터티 데이터 모델 디자이너](http://msdn.microsoft.com/library/4ccd7ad6-b934-4f7c-82a0-cfd2d4a95faf)합니다.  
  
3.  연결 문자열을 정의합니다.  
  
     [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]는 개념적 모델에 대해 쿼리를 실행할 때 특별한 형식의 연결 문자열을 사용합니다. 이 연결 문자열은 모델과 매핑 파일 및 데이터 소스에 대한 연결 정보를 캡슐화합니다. 자세한 내용은 참조 [하는 방법: 연결 문자열 정의](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)합니다.  
  
4.  Visual Studio 프로젝트를 구성 합니다.  
  
     에 대 한 참조 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 어셈블리 및 모델과 매핑 파일을 Visual Studio 프로젝트에 추가 해야 합니다. 이러한 매핑 파일을 프로젝트에 추가하여 연결 문자열에 표시된 위치에 응용 프로그램과 함께 배포되도록 할 수 있습니다. 자세한 내용은 참조 [하는 방법: 수동으로 Entity Framework 프로젝트 구성](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)합니다.  
  
## <a name="considerations-for-applications-with-existing-objects"></a>기존 개체가 있는 응용 프로그램에 대한 고려 사항  
 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 4부터 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]는 지속성 무시 개체라고도 하는 POCO(Plain Old CLR Object)를 지원합니다. 대부분의 경우 기존 개체는 적은 부분만 변경하여 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]와 작동할 수 있습니다. 자세한 내용은 참조 [POCO 엔터티 작업](http://msdn.microsoft.com/library/5e0fb82a-b6d1-41a1-b37b-c12db61629d3)합니다. 응용 프로그램을 마이그레이션할 수도 있습니다는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Entity Framework 도구에서 생성 되는 데이터 클래스를 사용 하 고 있습니다. 자세한 내용은 참조 [하는 방법: 엔터티 데이터 모델 마법사를 사용 하 여](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)합니다.  
  
## <a name="considerations-for-applications-that-use-adonet-providers"></a>ADO.NET 공급자를 사용하는 응용 프로그램에 대한 고려 사항  
 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] SqlClient와 같은 공급자를 사용 하면 표 형식 데이터를 반환 하는 데이터 원본의 쿼리할 수 있도록 합니다. 에 데이터를 로드할 수는 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] 데이터 집합입니다. 다음 목록에서는 기존 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] 공급자를 사용하는 응용 프로그램을 업그레이드할 때 고려할 사항에 대해 설명합니다.  
  
 데이터 판독기를 사용하여 표 형식 데이터 표시  
 실행 하는 것을 고려할 수 있는 [!INCLUDE[esql](../../../../../includes/esql-md.md)] EntityClient 공급자를 사용 하 여 쿼리하고 반환 된 전체를 열거 하 <xref:System.Data.EntityClient.EntityDataReader> 개체입니다. 응용 프로그램이 데이터 판독기를 사용하여 표 형식 데이터를 표시하며 데이터를 개체로 구체화, 변경 내용 추적 및 업데이트를 위해 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서 제공하는 기능이 필요하지 않은 경우에만 이 작업을 수행합니다. 데이터 소스를 업데이트하는 기존 데이터 액세스 코드를 계속 사용할 수 있지만 <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A>의 <xref:System.Data.EntityClient.EntityConnection> 속성에서 액세스된 기존 연결을 사용할 수도 있습니다. 자세한 내용은 참조 [Entity Framework 용 EntityClient 공급자](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)합니다.  
  
 DataSets 사용  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 변경 내용 추적, 데이터 바인딩 및 XML 데이터로 개체를 직렬화 하는 작업 메모리에 지 속성을 포함 하 여 DataSet에 의해 제공 된 동일한 기능을 대부분 제공 합니다. 자세한 내용은 참조 [개체 작업](../../../../../docs/framework/data/adonet/ef/working-with-objects.md)합니다.  
  
 경우는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 기능을 제공 하지 않는 응용 프로그램에 필요한 데이터 집합의 있습니다 계속 이용할 수 LINQ 쿼리의 이점의를 사용 하 여 [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)]합니다. 자세한 내용은 [LINQ to DataSet](../../../../../docs/framework/data/adonet/linq-to-dataset.md)를 참조하세요.  
  
## <a name="considerations-for-applications-that-bind-data-to-controls"></a>데이터를 컨트롤에 바인딩하는 응용 프로그램에 대한 고려 사항  
 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 여 DataSet 또는와 같은 데이터 원본에서에서 데이터를 캡슐화 할 수 있습니다 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] 데이터 소스 컨트롤을 마우스 다음 사용자 인터페이스 요소에 이러한 데이터 컨트롤을 바인딩할 합니다. 다음 목록에서는 컨트롤을 Entity Framework 데이터에 바인딩할 때 고려할 사항에 대해 설명합니다.  
  
 컨트롤에 데이터 바인딩  
 개념적 모델을 쿼리할 때는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 엔터티 형식의 인스턴스인 개체로 데이터를 반환 합니다. 이러한 개체를 직접 컨트롤에 바인딩될 수 및이 바인딩은 업데이트를 지원 합니다. 행과 같이 컨트롤의에서 데이터를 변경 하는이 의미는 <xref:System.Windows.Forms.DataGridView>을 자동으로 데이터베이스에 저장 하는 경우는 <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> 메서드를 호출 합니다.  
  
 응용 프로그램에서 쿼리 결과를 열거하여 <xref:System.Windows.Forms.DataGridView> 또는 데이터 바인딩을 지원하는 다른 형식의 컨트롤에 데이터를 표시하는 경우 응용 프로그램을 수정하여 컨트롤을 <xref:System.Data.Objects.ObjectQuery%601>의 결과에 바인딩할 수 있습니다.  
  
 자세한 내용은 참조 [컨트롤에 개체 바인딩](http://msdn.microsoft.com/library/2fd34855-929b-4303-a91e-4bb69d958f2b)합니다.  
  
 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] 데이터 소스 컨트롤  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 에서 데이터 바인딩을 단순화 하기는 데이터 소스 컨트롤이 포함 되어 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] 웹 응용 프로그램입니다. 자세한 내용은 참조 [Entity Framework 데이터 소스 컨트롤](http://msdn.microsoft.com/library/1f09af00-9578-4744-a029-765710a3c83f)합니다.  
  
## <a name="other-considerations"></a>기타 고려 사항  
 특정 종류의 응용 프로그램을 Entity Framework로 마이그레이션할 때 다음 사항을 고려해야 할 수도 있습니다.  
  
 데이터 서비스를 노출하는 응용 프로그램  
 WCF(Windows Communication Foundation)를 기반으로 하는 웹 서비스와 응용 프로그램은 XML 요청/응답 메시징 형식을 사용하여 기본 데이터 소스의 데이터를 노출합니다. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서는 이진, XML 또는 WCF 데이터 계약 serialization을 사용하여 엔터티 개체의 serialization을 지원합니다. 이진 및 WCF serialization은 모두 개체 그래프의 전체 serialization을 지원합니다. 자세한 내용은 참조 [N 계층 응용 프로그램 빌드](http://msdn.microsoft.com/library/9439d2ba-6b5f-44e8-be65-8a442d922cbb)합니다.  
  
 XML 데이터를 사용하는 응용 프로그램  
 개체 serialization을 사용하여 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 데이터 서비스를 만들 수 있습니다. 이러한 서비스는 AJAX 기반 인터넷 응용 프로그램과 같이 XML 데이터를 사용하는 응용 프로그램에 데이터를 제공합니다. 이런 경우 [!INCLUDE[ssAstoria](../../../../../includes/ssastoria-md.md)]를 사용하는 것이 좋습니다. 이러한 데이터 서비스 엔터티 데이터 모델을 기반으로 하 고 표준 REPRESENTATIONAL State Transfer () HTTP 작업을 사용 하 여 엔터티 데이터에 대 한 동적 액세스를 제공와 같은 GET, PUT 및 게시 합니다. 자세한 내용은 참조 [WCF 데이터 서비스 4.5](../../../../../docs/framework/data/wcf/index.md)합니다.  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서는 기본 XML 데이터 형식을 지원하지 않습니다. 즉, XML 열이 있는 테이블에 엔터티를 매핑할 때 XML 열에 해당하는 엔터티 속성은 문자열입니다. 개체의 연결을 끊고 XML로 serialize할 수 있습니다. 자세한 내용은 참조 [개체 직렬화](http://msdn.microsoft.com/library/06c77f9b-5b2e-4c78-b3e3-8c148ba0ea99)합니다.  
  
 응용 프로그램에 XML 데이터 쿼리 기능이 필요한 경우에도 LINQ to XML을 사용하여 LINQ 쿼리의 이점을 활용할 수 있습니다. 자세한 내용은 참조 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)합니다.  
  
 상태를 유지하는 응용 프로그램  
 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] 웹 응용 프로그램 또는 사용자 세션의 웹 페이지의 상태를 유지 자주 해야 합니다. 개체에 <xref:System.Data.Objects.ObjectContext> 인스턴스 수는 서버에서 세션 상태 또는 클라이언트 보기 상태나에 저장 하 고 나중에 검색 하 고 새 개체 컨텍스트에 다시 연결 합니다. 자세한 내용은 참조 [연결 및 분리 개체](http://msdn.microsoft.com/library/41d5c1ef-1b78-4502-aa10-7e1438d62d23)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [배포 고려 사항](../../../../../docs/framework/data/adonet/ef/deployment-considerations.md)  
 [Entity Framework 용어](../../../../../docs/framework/data/adonet/ef/terminology.md)
