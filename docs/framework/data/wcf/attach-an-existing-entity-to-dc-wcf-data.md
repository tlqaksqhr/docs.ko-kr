---
title: '방법: 기존 엔터티를 DataServiceContext에 연결(WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 30a0c0eb618dc7cedc8be2be4a327d9b1f73a51b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>방법: 기존 엔터티를 DataServiceContext에 연결(WCF Data Services)
엔터티 데이터 서비스에 이미 있는 경우는 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 클라이언트 라이브러리에 직접 엔터티를 나타내는 개체를 연결할 수 있게 된 <xref:System.Data.Services.Client.DataServiceContext> 첫 번째 하지 않고 쿼리를 실행 합니다. 자세한 내용은 참조 [데이터 서비스 업데이트](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)합니다.  
  
 이 항목의 예제에서는 Northwind 샘플 데이터 서비스 및 자동 생성된 클라이언트 데이터 서비스 클래스를 사용합니다. 완료 하면이 서비스 및 클라이언트 데이터 클래스 생성 됩니다는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 데이터 서비스에 저장될 변경 내용이 포함되어 있는 기존 `Customer` 개체를 만드는 방법을 보여 줍니다. 개체가 컨텍스트에 연결되고 <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> 메서드가 호출되어 <xref:System.Data.Services.Client.EntityStates.Modified> 메서드를 호출하기 전에 연결된 개체를 <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>로 표시합니다.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>참고 항목  
 [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
