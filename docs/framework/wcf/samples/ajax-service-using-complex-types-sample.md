---
title: AJAX Service Using Complex Types 샘플
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: c284fbef36ee7f6dda725ba9a3db9b98fb1549ed
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33804081"
---
# <a name="ajax-service-using-complex-types-sample"></a>AJAX Service Using Complex Types 샘플
이 샘플에는 복합 형식의 인스턴스를 만들고 서비스 및 클라이언트도 개체 JSON (JavaScript Notation) 사이 전송 하는 ASP.NET Asynchronous JavaScript and XML (AJAX) 서비스를 만들 Windows Communication Foundation (WCF)를 사용 하는 방법을 보여 줍니다. 웹 브라우저 클라이언트에서 JavaScript 코드를 사용하여 AJAX 서비스에 액세스할 수 있습니다. 기반으로 하는이 샘플은 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플.  
  
 Wcf에서 AJAX 지원을 통해 ASP.NET AJAX와 함께 사용 되도록 최적화 되었습니다는 <xref:System.Web.UI.ScriptManager> 제어 합니다. ASP.NET AJAX와 함께 WCF를 사용 하는 예제를 참조 하십시오.는 [AJAX 샘플과](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 다음 샘플의 서비스는 AJAX 특정 코드가 없는 WCF 서비스입니다. <xref:System.ServiceModel.Web.WebGetAttribute> 특성이 적용되지 않으므로 기본 HTTP 동사("POST")가 사용됩니다. 서비스에는 `DoMath`라는 복합 형식을 반환하는 단일 작업인 `MathResult`가 있습니다. 복합 형식은 마찬가지로 AJAX 특정 코드가 없는 표준 데이터 계약 형식입니다.  

```csharp
[DataContract]  
public class MathResult  
{  
    [DataMember]  
    public double sum;  
    [DataMember]  
    public double difference;  
    [DataMember]  
    public double product;  
    [DataMember]  
    public double quotient;  
}  
```

 기본 AJAX 서비스 샘플에서와 마찬가지로, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용하여 서비스에 AJAX 끝점을 만듭니다.  
  
 클라이언트 웹 페이지 ComplexTypeClientPage.aspx를 클릭할 때 서비스를 호출 하는 ASP.NET 및 JavaScript 코드를 포함 합니다.는 **계산을 수행할** 페이지에서 단추입니다. 서비스를 호출 하는 코드의 JSON 본문을 생성 하 고 유사한 HTTP POST를 사용 하 여 전송 된 [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) 샘플.  
  
 서비스 호출에 성공한 후 결과 JavaScript 개체에서 개별 데이터 멤버(`sum`, `difference`, `product` 및 `quotient`)에 액세스할 수 있습니다.  

```javascript
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```

### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  에 설명 된 대로 ComplexTypeAjaxService.sln 솔루션을 구축 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
3.  로 이동 http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (열지 마십시오 ComplexTypeClientPage.aspx 브라우저의 프로젝트 디렉터리에서).  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a>참고 항목  
 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
