---
title: "AJAX Service Using Complex Types 샘플 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# AJAX Service Using Complex Types 샘플
이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 복합 형식의 인스턴스를 만들고 서비스 및 클라이언트 사이에서 이러한 인스턴스를 JSON\(JavaScript Object Notation\)으로 전송하는 ASP.NET AJAX\(Asynchronous JavaScript and XML\) 서비스를 만드는 방법을 보여 줍니다.웹 브라우저 클라이언트에서 JavaScript 코드를 사용하여 AJAX 서비스에 액세스할 수 있습니다.이 샘플은 [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플을 기반으로 합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 AJAX 지원은 <xref:System.Web.UI.ScriptManager> 컨트롤을 통해 ASP.NET AJAX와 함께 사용되도록 최적화되었습니다.ASP.NET AJAX와 함께 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용한 예제를 보려면 [AJAX Samples](http://msdn.microsoft.com/ko-kr/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)을 참조하십시오.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 다음 샘플의 서비스는 AJAX 특정 코드가 없는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.<xref:System.ServiceModel.Web.WebGetAttribute> 특성이 적용되지 않으므로 기본 HTTP 동사\("POST"\)가 사용됩니다.서비스에는 `MathResult`라는 복합 형식을 반환하는 단일 작업인 `DoMath`가 있습니다.복합 형식은 마찬가지로 AJAX 특정 코드가 없는 표준 데이터 계약 형식입니다.  
  
```  
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
  
 클라이언트 웹 페이지 ComplexTypeClientPage.aspx에는 사용자가 페이지에서 **계산 수행** 단추를 클릭했을 때 서비스를 호출하기 위한 ASP.NET 및 JavaScript 코드가 포함되어 있습니다.[AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) 샘플과 비슷하게 서비스를 호출하기 위한 코드는 JSON 본문을 생성하고 HTTP POST를 사용하여 전송합니다.  
  
 서비스 호출에 성공한 후 결과 JavaScript 개체에서 개별 데이터 멤버\(`sum`, `difference`, `product` 및 `quotient`\)에 액세스할 수 있습니다.  
  
```  
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
  
```  
  
### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행했는지 확인합니다.  
  
2.  [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)에 설명된 대로 ComplexTypeAjaxService.sln 솔루션을 빌드합니다.  
  
3.  http:\/\/localhost\/ServiceModelSamples\/ComplexTypeClientPage.aspx로 이동합니다. 브라우저에서 프로젝트 디렉터리의 ComplexTypeClientPage.aspx를 열지 마십시오.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## 참고 항목  
 [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md)