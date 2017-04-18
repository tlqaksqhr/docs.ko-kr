---
title: "ASP.NET 호환성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# ASP.NET 호환성
이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 호환 모드를 사용하도록 설정하는 방법을 보여 줍니다.  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 호환 모드에서 실행되는 서비스는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램 파이프라인에 완전히 참여하고 파일\/URL 권한 부여, 세션 상태 및 <xref:System.Web.HttpContext> 클래스와 같은 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 기능을 활용할 수 있습니다.  <xref:System.Web.HttpContext> 클래스는 쿠키, 세션 및 기타 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 기능에 대한 액세스를 허용합니다.  이 모드에서는 바인딩에 HTTP 전송이 사용되고 서비스 자체가 IIS에서 호스트되어야 합니다.  
  
 이 샘플에서 클라이언트는 콘솔 응용 프로그램\(실행 파일\)이고 서비스는 IIS\(인터넷 정보 서비스\)에서 호스트됩니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
> [!NOTE]
>  이 샘플을 실행하려면 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 응용 프로그램 풀이 필요합니다.  새 응용 프로그램 풀을 만들거나 기본 응용 프로그램 풀을 수정하려면 다음 단계를 따릅니다.  
>   
>  1.  **제어판**을 엽니다.  **시스템 및 보안** 머리글 아래의 **관리 도구** 애플릿을 엽니다.  **IIS\(인터넷 정보 서비스\) 관리자** 애플릿을 엽니다.  
> 2.  **연결** 창의 트리 뷰를 확장합니다.  **응용 프로그램 풀** 노드를 선택합니다.  
> 3.  기본 응용 프로그램 풀에서 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]을 사용하도록 설정하려면\(이 경우 기존 사이트와 비호환성 문제가 발생할 수 있음\) **DefaultAppPool** 목록 항목을 마우스 오른쪽 단추로 클릭하고 **기본 설정…**을 선택합니다.  **.Net Framework 버전** 풀다운을 **.Net Framework v4.0.30128**\(이상\)로 설정합니다.  
> 4.  다른 응용 프로그램의 호환성을 유지하기 위해 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]을 사용하는 새 응용 프로그램 풀을 만들려면 **응용 프로그램 풀** 노드를 마우스 오른쪽 단추로 클릭하고 **응용 프로그램 풀 추가…**를 선택합니다.  새 응용 프로그램 풀의 이름을 지정하고 **.Net Framework 버전** 풀다운을 **.Net Framework v4.0.30128**\(이상\)로 설정합니다.  아래의 설치 단계를 실행한 후 **ServiceModelSamples** 응용 프로그램을 마우스 오른쪽 단추로 클릭하고 **응용 프로그램 관리**, **고급 설정…**을 차례로 선택합니다.  **응용 프로그램 풀**을 새 응용 프로그램 풀로 설정합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.  계속하기 전에 다음\(기본\) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [.NET Framework 4용 WCF\(Windows Communication Foundation\) 및 Windows WF\(Workflow Foundation\) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780)\(영문\)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.  이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 이 샘플은 계산기 서비스를 구현하는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)을 기반으로 합니다.  실행 결과를 유지하면서 일련의 작업을 수행할 수 있도록 `ICalculator` 계약은 `ICalculatorSession` 계약으로 수정되었습니다.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculatorSession  
{  
    [OperationContract]  
    void Clear();  
    [OperationContract]  
    void AddTo(double n);  
    [OperationContract]  
    void SubtractFrom(double n);  
    [OperationContract]  
    void MultiplyBy(double n);  
    [OperationContract]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
  
```  
  
 계산을 수행하기 위해 여러 서비스 작업이 호출될 때 서비스는 이 기능을 사용하여 각 클라이언트에 대한 상태를 유지 관리합니다.  클라이언트는 `Result`를 호출하여 현재 결과를 검색하고 `Clear`를 호출하여 결과를 0으로 지울 수 있습니다.  
  
 서비스는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 세션을 사용하여 각 클라이언트 세션의 결과를 저장합니다.  따라서 서비스는 여러 서비스 호출에서 각 클라이언트에 대한 실행 결과를 유지 관리할 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 세션 상태와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 세션은 전혀 다릅니다.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 세션에 대한 자세한 내용은 [세션](../../../../docs/framework/wcf/samples/session.md)을 참조하세요.  
  
 서비스는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 세션 상태에 크게 의존하며 올바른 작동을 위해 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 호환 모드가 필요합니다.  이러한 요구 사항은 `AspNetCompatibilityRequirements` 특성을 적용하여 선언적으로 표현됩니다.  
  
```  
[AspNetCompatibilityRequirements(RequirementsMode =  
                       AspNetCompatibilityRequirementsMode.Required)]  
public class CalculatorService : ICalculatorSession  
{  
    double Result  
    {  // store result in AspNet Session  
       get {  
          if (HttpContext.Current.Session["Result"] != null)  
             return (double)HttpContext.Current.Session["Result"];  
          return 0.0D;  
       }  
       set  
       {  
          HttpContext.Current.Session["Result"] = value;  
       }  
    }  
    public void Clear()  
    {  
        Result = 0.0D;  
    }  
    public void AddTo(double n)  
    {  
        Result += n;  
    }  
    public void SubtractFrom(double n)  
    {  
        Result -= n;  
    }  
    public void MultiplyBy(double n)  
    {  
        Result *= n;  
    }  
    public void DivideBy(double n)  
    {  
        Result /= n;  
    }  
    public double Result()  
    {  
        return Result;  
    }  
}  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.  클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```  
  
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
  
```  
  
### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행했는지 확인합니다.  
  
2.  C\# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  솔루션을 빌드한 후 Setup.bat를 실행하여 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]에 ServiceModelSamples 응용 프로그램을 설치합니다.  이제 ServiceModelSamples 디렉터리가 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 응용 프로그램으로 나타납니다.  
  
4.  단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따릅니다.  
  
## 참고 항목  
 [AppFabric 호스팅 및 지속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)