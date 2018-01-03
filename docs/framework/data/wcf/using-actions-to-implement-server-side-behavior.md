---
title: "동작을 사용하여 서버 쪽 동작 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11a372db-7168-498b-80d2-9419ff557ba5
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9d8ca19a5a49815130103672f43452ebbfedfae3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-actions-to-implement-server-side-behavior"></a>동작을 사용하여 서버 쪽 동작 구현
OData 동작을 통해 OData 서비스에서 검색한 리소스에 따른 동작을 구현할 수 있습니다.  예를 들어 디지털 영화를 리소스로 가정하면, 체크 아웃, 등급/코멘트 또는 체크 인 등 디지털 영화와 관련하여 수행할 수 있는 여러 동작이 있습니다. 이러한 동작은 디지털 영화를 관리하는 WCF Data Service로 구현할 수 있는 동작의 예입니다. 동작은 동작을 호출할 수 있는 리소스를 포함하는 OData 응답에 설명되어 있습니다. 사용자가 디지털 영화를 나타내는 리소스를 요청하면 WCF Data Service에서 반환된 응답은 해당 리소스에서 사용할 수 있는 동작에 대한 정보를 포함합니다. 동작의 사용 가능 여부는 데이터 서비스 또는 리소스의 상태에 따라 달라질 수 있습니다. 예를 들어 디지털 영화를 체크 아웃하면 다른 사용자가 이 디지털 영화를 체크 아웃할 수 없습니다. 클라이언트는 URL을 지정하기만 하면 동작을 호출할 수 있습니다. 예를 들어 http://MyServer/MovieService.svc/Movies(6)는 특정 디지털 영화를 식별하고 http://MyServer/MovieService.svc/Movies(6)/Checkout은 특정 영화에서 동작을 호출합니다. 동작을 사용하여 데이터 모델을 노출하지 않고 서비스 모델을 노출할 수 있습니다. 영화 서비스를 계속 예로 들자면 사용자가 영화의 평점을 매길 수 있도록 하지만 등급 데이터를 리소스로 직접적으로 노출하지 않도록 할 수 있습니다. 사용자가 영화에 대한 평점을 매길 수 있지만 평가 데이터를 리소스로 직접 액세스하지 않도록 평가 동작을 구현할 수 있습니다.  
  
## <a name="implementing-an-action"></a>동작 구현  
 구현 해야 하는 서비스 동작을 구현 하는 <xref:System.IServiceProvider>, [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx), 및 [IDataServiceInvokable](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceinvokable(v=vs.113).aspx) 인터페이스입니다. <xref:System.IServiceProvider>WCF Data Services의 사용자 구현을를 허용 [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx)합니다. [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx) 를 만들려면 WCF Data Services를 사용 하면 찾기, 설명 및 서비스 작업을 호출 합니다. [IDataServiceInvokable](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceinvokable(v=vs.113).aspx) 있는 경우 서비스 동작의 동작을 구현 하는 코드를 호출 하 고 결과 얻을 수 있습니다. WCF Data Services가 Per-Call WCF Services이고 서비스를 호출할 때마다 서비스의 새 인스턴스가 만들어진다는 점에 주의합니다.  서비스를 만들 때 불필요한 동작이 수행되지 않는지 확인합니다.  
  
### <a name="iserviceprovider"></a>IServiceProvider  
 <xref:System.IServiceProvider>는 <xref:System.IServiceProvider.GetService%2A>라는 메서드를 포함합니다. 이 메서드는 WCF Data Services에 의해 호출되어 메타데이터 서비스 공급자 및 데이터 동작 공급자를 비롯하여 여러 서비스 공급자를 가져옵니다. 데이터 서비스 동작 공급자에 대 한 메시지가 표시 되 면 반환 프로그램 [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx) 구현 합니다.  
  
### <a name="idataserviceactionprovider"></a>IDataServiceActionProvider  
 [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx) 사용 가능한 작업에 대 한 정보를 검색할 수 있도록 하는 메서드가 포함 되어 있습니다. 구현 하는 경우 [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx) 서비스의 구현에 의해 정의 된 서비스에 대 한 메타 데이터를 확대는 [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider(v=vs.113).aspx) 동작이 포함 된 및 적절 하 게 이러한 작업에 디스패치를 처리 중입니다.  
  
#### <a name="advertiseserviceaction"></a>AdvertiseServiceAction  
 [IDataServiceActionProvider](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider.advertiseserviceaction(v=vs.113).aspx) 호출 되어 지정된 된 리소스를 사용할 수 있는 동작을 확인 합니다. 이 메서드는 항상 사용할 수 있는 것은 아닌 동작에 대해서만 호출됩니다. 요청 중인 리소스 상태 또는 서비스의 상태를 기반으로 하는 OData 응답에 동작을 포함해야 하는지 여부를 확인할 때 사용됩니다. 이를 확인하는 방법은 전적으로 사용자의 재량에 따라 결정됩니다. 가용성을 계산하는 비용이 높거나 현재 리소스가 피드에 있는 경우 확인을 건너뛰고 동작을 알려도 됩니다. 반환 중인 현재 리소스가 피드의 일부인 경우 `inFeed` 매개 변수가 `true`로 설정됩니다.  
  
#### <a name="createinvokable"></a>CreateInvokable  
 [CreateInvokable](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceactionprovider.createinvokable(v=vs.113).aspx) 을 만들기 위해 호출 됩니다는 [IDataServiceInvokable](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceinvokable(v=vs.113).aspx) 동작의 동작을 구현 하는 코드를 캡슐화 하는 대리자를 포함 하 합니다. 그렇기 때문에 [IDataServiceInvokable](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceinvokable(v=vs.113).aspx) 인스턴스를 만들지만 동작을 호출 하지 않습니다. WCF Data Service 동작은 의도하지 않은 결과를 포함할 수 있고 이러한 변경 내용을 디스크에 저장하도록 업데이트 공급자와 함께 사용해야 합니다. [IDataServiceInvokable.Invoke](https://msdn.microsoft.com/library/system.data.services.providers.idataserviceinvokable.invoke(v=vs.113).aspx) 메서드는 업데이트 공급자 savechanges ()에서 메서드를 호출 합니다.  
  
#### <a name="getserviceactions"></a>GetServiceActions  
 이 메서드는 컬렉션을 반환 [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx) WCF Data Service가 노출 하는 작업은 모두를 나타내는 경우. [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx) 작업 이름, 해당 매개 변수 및 반환 형식이 같은 정보를 포함 하는 동작의 메타 데이터 표현입니다.  
  
#### <a name="getserviceactionsbybindingparametertype"></a>GetServiceActionsByBindingParameterType  
 이 메서드는 모든 컬렉션을 반환 [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx) 지정 된 바인딩 매개 변수 형식에 바인딩할 수 있는 인스턴스. 즉, 모든 [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx)지정된 된 리소스 형식 (또는 바인딩 매개 변수 형식이 라고도 함)에 대해 작동할 수입니다. 이 서비스가 해당 리소스에 대해 호출할 수 있는 동작에 대 한 정보를 포함 하기 위해 리소스를 반환 하는 경우 사용 됩니다. 이 메서드는 파생된 형식이 아닌 정확한 바인딩 매개 변수 형식을 바인딩할 수 있는 동작만 반환해야 합니다. 이 메서드는 발생하는 형식 당 요청마다 한 번만 호출되며 결과는 WCF Data Services에서 캐시합니다.  
  
#### <a name="tryresolveserviceaction"></a>TryResolveServiceAction  
 이 메서드는 지정 된 검색 [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx) 반환 `true` 경우는 [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx) 를 찾을 수 있습니다. 하는 경우 발견는 [ServiceAction](https://msdn.microsoft.com/library/system.data.services.providers.serviceaction(v=vs.113).aspx) 에 반환 되는 `serviceAction``out` 매개 변수입니다.  
  
### <a name="idataserviceinvokable"></a>IDataServiceInvokable  
 이 인터페이스는 WCF Data Service 동작을 실행하는 방법을 제공합니다. IDataServiceInvokable을 구현하는 경우 다음 세 가지 작업을 수행해야 합니다.  
  
1.  매개 변수를 캡처하고 잠재적으로 마샬링합니다.  
  
2.  Invoke()가 호출될 때 동작을 실제로 구현하는 코드에 매개 변수를 디스패치합니다.  
  
3.  GetResult()를 사용하여 결과를 검색할 수 있도록 Invoke()에서 결과를 저장합니다.  
  
 매개 변수를 토큰으로 전달할 수 있습니다. 이는 실제 동작에 디스패치하기 전에 이러한 토큰을 실제 리소스로 변환(마샬링)해야 할 수 있는 경우 리소스를 나타내는 토큰과 함께 작동하는 데이터 서비스 공급자를 쓸 수 있기 때문입니다. 매개 변수를 마샬링한 후 동작이 호출될 때 발생하는 리소스에 대한 변경 내용을 디스크에 저장하고 쓸 수 있도록 매개 변수가 편집 가능한 상태여야 합니다.  
  
 이 인터페이스에는 Invoke 및 GetResult의 두 가지 메서드가 필요합니다. Invoke는 동작의 동작을 구현하는 대리자를 호출하고 GetResult는 동작의 결과를 반환합니다.  
  
## <a name="invoking-a-wcf-data-service-action"></a>WCF Data Service 동작 호출  
 동작은 HTTP POST 요청을 사용하여 호출됩니다. URL은 뒤에 동작 이름이 오늘 리소스를 지정합니다. 요청 본문에서 매개 변수가 전달됩니다. 예를 들어 Rate라는 동작을 노출한 MovieService라는 서비스가 있는 경우입니다. 다음 URL을 사용하여 특정 영화에서 Rate 동작을 호출할 수 있습니다.  
  
 http://MovieServer/MovieService.svc/Movies(1)/Rate  
  
 Movies(1)은 평점을 매길 영화를 지정하고 Rate는 Rate 동작을 지정합니다. 등급의 실제 값은 다음 예에서와 같이 HTTP 요청의 본문에 있습니다.  
  
```  
POST http://MovieServer/MoviesService.svc/Movies(1)/Rate HTTP/1.1   
Content-Type: application/json   
Content-Length: 20   
Host: localhost:15238  
{   
   "rating": 4   
}  
```  
  
> [!WARNING]
>  위의 샘플 코드는 JSON 경량 버전을 지원하는 WCF Data Services 5.2 이상에서만 작동합니다. 이전 버전의 WCF Data Services를 사용할 경우 `application/json;odata=verbose`와 같이 자세한 JSON 콘텐츠 형식을 지정해야 합니다.  
  
 또는 다음 코드 조각에서와 같이 WCF Data Services 클라이언트를 사용하는 동작을 호출할 수 있습니다.  
  
```  
MoviesModel context = new MoviesModel (new Uri("http://MyServer/MoviesService.svc/"));  
            //...  
            context.Execute(new Uri("http://MyServer/MoviesService.svc/Movies(1)/Rate"), "POST", new BodyOperationParameter("rating",4) );           
```  
  
 위의 코드 조각에서 `MoviesModel` 클래스는 Visual Studio를 사용하여 서비스 참조를 WCF Data Service에 추가하여 생성되었습니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF Data Services 4.5](../../../../docs/framework/data/wcf/index.md)  
 [WCF Data Services 정의](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [WCF Data Services 개발 및 배포](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)  
 [사용자 지정 데이터 서비스 공급자](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)
