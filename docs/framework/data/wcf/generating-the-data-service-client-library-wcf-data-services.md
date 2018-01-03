---
title: "데이터 서비스 클라이언트 라이브러리 생성(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6adbaafe170cf3f5398677d5df3b3d2ff0a95abe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a><span data-ttu-id="b0cf1-102">데이터 서비스 클라이언트 라이브러리 생성(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="b0cf1-102">Generating the Data Service Client Library (WCF Data Services)</span></span>
<span data-ttu-id="b0cf1-103">구현 하는 데이터 서비스는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 의해 노출 된 데이터 모델을 설명 하는 서비스 메타 데이터 문서를 반환할 수 있습니다는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드입니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-103">A data service that implements the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] can return a service metadata document that describes the data model exposed by the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.</span></span> <span data-ttu-id="b0cf1-104">자세한 내용은 참조 [OData: 서비스 메타 데이터 문서](http://go.microsoft.com/fwlink/?LinkId=186070)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-104">For more information, see [OData: Service Metadata Document](http://go.microsoft.com/fwlink/?LinkId=186070).</span></span> <span data-ttu-id="b0cf1-105">사용할 수는 **서비스 참조 추가** 대화 상자에 대 한 참조를 추가 하려면 Visual Studio에는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-기반 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-105">You can use the **Add Service Reference** dialog in Visual Studio to add a reference to an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service.</span></span> <span data-ttu-id="b0cf1-106">반환 된 메타 데이터에 대 한 참조를 추가 하려면이 도구를 사용 하면는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 다음 작업을 수행 클라이언트 프로젝트에서 피드를:</span><span class="sxs-lookup"><span data-stu-id="b0cf1-106">When you use this tool to add a reference to the metadata returned by an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in a client project, it performs the following actions:</span></span>  
  
-   <span data-ttu-id="b0cf1-107">데이터 서비스에서 서비스 메타데이터 문서를 요청하고 반환된 메타데이터를 해석합니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-107">Requests the service metadata document from the data service and interprets the returned metadata.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0cf1-108">반환된 메타데이터는 클라이언트 프로젝트에 .edmx 파일로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-108">The returned metadata is stored in the client project as an .edmx file.</span></span> <span data-ttu-id="b0cf1-109">이 .edmx 파일은 Entity Framework에서 사용되는 .edmx 파일과 동일한 형식을 사용하지 않기 때문에 엔터티 데이터 모델 디자이너를 사용하여 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-109">This .edmx file cannot be opened by using the Entity Data Model designer because it does not have the same format an .edmx file used by the Entity Framework.</span></span> <span data-ttu-id="b0cf1-110">XML 편집기나 텍스트 편집기를 사용하여 이 메타데이터 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-110">You can view this metadata file by using the XML editor or any text editor.</span></span> <span data-ttu-id="b0cf1-111">자세한 내용은 참조는 [ \[MC-EDMX\]: 데이터 서비스 패키징 형식의 엔터티 데이터 모델](http://go.microsoft.com/fwlink/?LinkID=178833) 사양</span><span class="sxs-lookup"><span data-stu-id="b0cf1-111">For more information, see the [\[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](http://go.microsoft.com/fwlink/?LinkID=178833) specification</span></span>  
  
-   <span data-ttu-id="b0cf1-112"><xref:System.Data.Services.Client.DataServiceContext>에서 상속된 엔터티 컨테이너 클래스로 서비스 표현을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-112">Generates a representation of the service as an entity container class that inherits from <xref:System.Data.Services.Client.DataServiceContext>.</span></span> <span data-ttu-id="b0cf1-113">생성된 이 엔터티 컨테이너 클래스는 엔터티 데이터 모델 도구에서 생성하는 엔터티 컨테이너와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-113">This generated entity container class resembles the entity container that the Entity Data Model tools generate.</span></span> <span data-ttu-id="b0cf1-114">자세한 내용은 [개체 서비스 개요(Entity Framework)](http://msdn.microsoft.com/en-us/43014cf9-c9cb-4538-bfbb-197820b60038)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-114">For more information, see [Object Services Overview (Entity Framework)](http://msdn.microsoft.com/en-us/43014cf9-c9cb-4538-bfbb-197820b60038).</span></span>  
  
-   <span data-ttu-id="b0cf1-115">서비스 메타데이터에서 검색한 데이터 모델 형식에 대해 데이터 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-115">Generates data classes for the data model types that it discovers in the service metadata.</span></span>  
  
-   <span data-ttu-id="b0cf1-116">프로젝트에 `System.Data.Services.Client` 어셈블리 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-116">Adds a reference to the `System.Data.Services.Client` assembly to the project.</span></span>  
  
 <span data-ttu-id="b0cf1-117">자세한 내용은 참조 [하는 방법: 데이터 서비스 참조 추가](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-117">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="b0cf1-118">클라이언트 데이터 서비스 클래스를 사용 하 여 생성할 수도 있습니다는 [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) 명령 프롬프트 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-118">The client data service classes can also be generated by using the [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) tool at the command prompt.</span></span> <span data-ttu-id="b0cf1-119">자세한 내용은 참조 [하는 방법: 수동으로 클라이언트 데이터 서비스 클래스 생성](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-119">For more information, see [How to: Manually Generate Client Data Service Classes](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).</span></span>  
  
## <a name="client-data-type-mapping"></a><span data-ttu-id="b0cf1-120">클라이언트 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="b0cf1-120">Client Data Type Mapping</span></span>  
 <span data-ttu-id="b0cf1-121">사용 하는 경우는 **서비스 참조 추가** 대화 상자에 Visual Studio 또는 `DataSvcUtil.exe` 기반으로 하는 클라이언트 데이터 클래스를 생성 하는 도구는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드,.NET Framework 데이터 형식에서 기본 형식에 매핑된는 데이터 모델이 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-121">When you use the **Add Service Reference** dialog in Visual Studio or the `DataSvcUtil.exe` tool to generate client data classes that are based on an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, the .NET Framework data types are mapped to the primitive types from the data model as follows:</span></span>  
  
|<span data-ttu-id="b0cf1-122">데이터 모델 형식</span><span class="sxs-lookup"><span data-stu-id="b0cf1-122">Data model type</span></span>|<span data-ttu-id="b0cf1-123">.NET Framework 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b0cf1-123">.NET Framework data type</span></span>|  
|---------------------|------------------------------|  
|`Edm.Binary`|<span data-ttu-id="b0cf1-124"><xref:System.Byte> `[]`</span><span class="sxs-lookup"><span data-stu-id="b0cf1-124"><xref:System.Byte> `[]`</span></span>|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 <span data-ttu-id="b0cf1-125">자세한 내용은 참조 [OData: 기본 데이터 형식](http://go.microsoft.com/fwlink/?LinkId=186072)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0cf1-125">For more information, see [OData: Primitive Data Types](http://go.microsoft.com/fwlink/?LinkId=186072).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0cf1-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0cf1-126">See Also</span></span>  
 [<span data-ttu-id="b0cf1-127">WCF Data Services 클라이언트 라이브러리</span><span class="sxs-lookup"><span data-stu-id="b0cf1-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [<span data-ttu-id="b0cf1-128">빠른 시작</span><span class="sxs-lookup"><span data-stu-id="b0cf1-128">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
