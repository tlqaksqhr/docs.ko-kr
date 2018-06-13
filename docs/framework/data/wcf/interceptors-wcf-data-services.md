---
title: 인터셉터(WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: f3ff08dd4cd20e7ce226750a386cfddb27731923
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363802"
---
# <a name="interceptors-wcf-data-services"></a>인터셉터(WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 응용을 프로그램 작업에 사용자 지정 논리를 추가할 수 있도록 요청 메시지를 가로챌 수 있습니다. 들어오는 메시지의 데이터 유효성 검사에이 사용자 지정 논리를 사용할 수 있습니다. 요청별로 사용자 지정 인증 정책을 삽입하는 등 쿼리 요청 범위를 추가로 제한하는 데에도 이 논리를 사용할 수 있습니다.  
  
 가로채기는 데이터 서비스에서 특별한 특성이 있는 메서드에 의해 수행됩니다. 이러한 메서드는 메시지 처리 중 적절한 시점에 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]에서 호출됩니다. 인터셉터 메서드는 서비스 작업과 달리 요청의 매개 변수를 받아들일 수 없습니다 및 인터셉터는 엔터티 집합 별로 정의 됩니다. HTTP GET 요청을 처리할 때을 호출 되는 쿼리 인터셉터 메서드는 쿼리 결과에서 인터셉터의 엔터티 인스턴스가 설정 여부를 결정 하는 람다 식을 반환할지 반환 해야 합니다. 데이터 서비스는 이 식을 사용하여 요청된 작업을 보다 구체화합니다. 다음은 쿼리 인터셉터의 정의 예제입니다.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 자세한 내용은 참조 [하는 방법: 데이터 서비스 메시지 가로채기](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md)합니다.  
  
 쿼리가 아닌 작업을 처리할 때 호출되는 변경 인터셉터는 `void`(Visual Basic에서는 `Nothing`)를 반환해야 합니다. 변경 인터셉터 메서드는 다음 두 매개 변수를 허용해야 합니다.  
  
1.  엔터티 집합의 엔터티 형식과 호환되는 형식의 매개 변수. 데이터 서비스에서 변경 인터셉터를 호출하는 경우 이 매개 변수의 값은 요청에서 보낸 엔터티 정보를 반영합니다.  
  
2.  <xref:System.Data.Services.UpdateOperations> 형식의 매개 변수. 데이터 서비스에서 변경 인터셉터를 호출하는 경우 이 매개 변수의 값은 요청에서 수행하려는 작업을 반영합니다.  
  
 다음은 변경 인터셉터의 정의 예제입니다.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 자세한 내용은 참조 [하는 방법: 데이터 서비스 메시지 가로채기](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md)합니다.  
  
 다음 특성은 가로채기에서 지원되지 않습니다.  
  
 **[QueryInterceptor (** *EnitySetName* **)]**  
 <xref:System.Data.Services.QueryInterceptorAttribute> 특성이 적용된 메서드는 대상 엔터티 집합 리소스에 대해 HTTP GET 요청을 받을 때 호출됩니다. 이 메서드는 항상 `Expression<Func<T,bool>>` 형식의 람다 식을 반환해야 합니다.  
  
 **[ChangeInterceptor (** *EnitySetName* **)]**  
 <xref:System.Data.Services.ChangeInterceptorAttribute> 특성이 적용된 메서드는 대상 엔터티 집합 리소스에 대해 HTTP GET 요청 이외의 HTTP 요청을 받을 때 호출됩니다. 이 메서드는 항상 `void`(Visual Basic에서는 `Nothing`)를 반환해야 합니다.  
  
 자세한 내용은 참조 [하는 방법: 데이터 서비스 메시지 가로채기](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서비스 작업](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)
