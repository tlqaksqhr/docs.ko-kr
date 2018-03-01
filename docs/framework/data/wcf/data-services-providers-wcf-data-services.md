---
title: "데이터 서비스 공급자(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: a0160b1b-3d9c-4cc8-8391-cb0986a60a41
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6f25f1f9137206c1adb3ab3f89b7c6a783aeccf0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="data-services-providers-wcf-data-services"></a>데이터 서비스 공급자(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]데이터를 노출 하기 위한 여러 공급자 모델을 지원 한 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드입니다. 이 항목에서 제공하는 정보를 통해 데이터 소스에 가장 적합한 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 공급자를 선택할 수 있습니다.  
  
## <a name="data-source-providers"></a>데이터 소스 공급자  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]데이터 서비스의 데이터 모델을 정의 하기 위한 다음 공급자를 지원 합니다.  
  
|공급자|설명|  
|--------------|-----------------|  
|Entity Framework 공급자|이 공급자는 ADO.NET Entity Framework를 사용하여 관계형 데이터에 매핑되는 데이터 모델 정의를 통해 데이터 서비스에 관계형 데이터를 사용할 수 있도록 합니다. 데이터 소스는 SQL Server 또는 Entity Framework에 대한 타사 공급자 지원이 있는 다른 모든 데이터 소스일 수 있습니다. SQL Server 데이터베이스와 같은 관계형 데이터 소스가 있는 경우 Entity Framework 공급자를 사용해야 합니다. 자세한 내용은 참조 [Entity Framework 공급자](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)합니다.|  
|리플렉션 공급자|이 공급자는 리플렉션을 사용하여 <xref:System.Linq.IQueryable%601> 인터페이스 인스턴스로 노출될 수 있는 기존 데이터 클래스를 기반으로 데이터 모델을 정의할 수 있도록 합니다. <xref:System.Data.Services.IUpdatable> 인터페이스를 구현하면 업데이트를 사용할 수 있습니다. LINQ to SQL에 의해 생성되었거나 형식화된 데이터 집합에 의해 정의된 클래스와 같이 런타임에 정의된 정적 데이터 클래스가 있는 경우 이 공급자를 사용해야 합니다. 자세한 내용은 참조 [리플렉션 공급자](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)합니다.|  
|사용자 지정 데이터 서비스 공급자|[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에 포함된 공급자 집합을 사용하면 런타임에 바인딩된 데이터 형식을 기반으로 데이터 모델을 동적으로 정의할 수 있습니다. 응용 프로그램을 디자인할 때 노출되는 데이터를 알 수 없거나 Entity Framework 또는 리플렉션 공급자가 충분하지 않은 경우 이러한 인터페이스를 구현해야 합니다. 자세한 내용은 참조 [사용자 지정 데이터 서비스 공급자](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)합니다.|  
  
## <a name="other-data-service-providers"></a>기타 데이터 서비스 공급자  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에 기타 공급자 중 하나를 사용 하 여 정의 된 데이터 소스의 성능을 높이 다음과 같은 추가 데이터 서비스 공급자입니다.  
  
|공급자|설명|  
|--------------|-----------------|  
|스트리밍 공급자|이 공급자를 사용하면 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 통해 BLOB(Binary Large Object) 데이터 형식을 노출할 수 있습니다. 스트리밍 공급자는 <xref:System.Data.Services.Providers.IDataServiceStreamProvider> 인터페이스를 구현하여 만듭니다. 이 공급자는 원하는 데이터 소스 공급자와 함께 구현할 수 있습니다. 자세한 내용은 참조 [스트리밍 공급자](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md)합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)  
 [데이터 서비스 호스팅](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)
