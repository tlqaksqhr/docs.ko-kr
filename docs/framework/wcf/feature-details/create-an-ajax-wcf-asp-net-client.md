---
title: "방법: AJAX 사용 WCF 서비스 및 해당 서비스에 액세스하는 ASP.NET 클라이언트 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aafa15129e4a131c5f50eb3296a87fc141e1bda6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a>방법: AJAX 사용 WCF 서비스 및 해당 서비스에 액세스하는 ASP.NET 클라이언트 만들기
이 항목에서는 Visual Studio 2008을 사용하여 AJAX 사용 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스 및 해당 서비스에 액세스하는 ASP.NET 클라이언트를 만드는 방법을 보여 줍니다. 서비스 및 클라이언트 코드의 경우 절차 단원에서 서비스 및 클라이언트를 만드는 단계에 대해 설명한 다음 예제 단원에서 설명합니다.  
  
### <a name="to-create-the-aspnet-client-application"></a>ASP.NET 클라이언트 응용 프로그램을 만들려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]를 엽니다.  
  
2.  **파일** 메뉴 선택 **새로**, 다음 **프로젝트**, 다음 **웹**를 선택한 후 **ASP.NET 웹 응용 프로그램**.  
  
3.  프로젝트 이름을 `SandwichServices` 클릭 **확인**합니다.  
  
### <a name="to-create-the-wcf-ajax-enabled-service"></a>WCF AJAX 사용 서비스를 만들려면  
  
1.  마우스 오른쪽 단추로 클릭는 `SandwichServices` 프로젝트에 **솔루션 탐색기** 창과 선택 **추가**, 다음 **새 항목**, 차례로 **AJAX 사용 WCF 서비스** .  
  
2.  서비스 이름을 `CostService` 에 **이름** 상자 한 클릭 **추가**합니다.  
  
3.  CostService.svc.cs 파일을 엽니다.  
  
4.  지정 된 `Namespace` 에 대 한 <xref:System.ServiceModel.ServiceContractAttribute> 으로 `SandwichService`:  
  
    ```  
    namespace SandwichServices  
    {  
      [ServiceContract(Namespace = "SandwichServices")]  
      [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
       public class CostService  
       {  
         …  
       }  
     }  
    ```  
  
5.  서비스에서 작업을 구현합니다. 각 작업에 <xref:System.ServiceModel.OperationContractAttribute>를 추가하여 계약의 일부라는 것을 나타냅니다. 다음 예제에서는 지정된 샌드위치 개수에 대한 비용을 반환하는 메서드를 구현합니다.  
  
    ```  
    public class CostService  
    {  
        [OperationContract]  
        public double CostOfSandwiches(int quantity)  
        {  
            return 1.25 * quantity;  
        }  
  
    // Add more operations here and mark them with [OperationContract]  
    }  
    ```  
  
### <a name="to-configure-the-client-to-access-the-service"></a>서비스에 액세스하도록 클라이언트를 구성하려면  
  
1.  Default.aspx 페이지를 열고 선택 된 **디자인** 보기.  
  
2.  **보기** 메뉴 선택 **도구 상자**합니다.  
  
3.  확장 하 고는 **AJAX 확장** 노드 및 끌어서 놓기는 **ScriptManager** Default.aspx 페이지에 로그온 합니다.  
  
4.  마우스 오른쪽 단추로 클릭는 **ScriptManager** 선택 **속성**합니다.  
  
5.  확장 된 **서비스** 컬렉션에는 **속성** 창을 엽니다는 **ServiceReference 컬렉션 편집기** 창.  
  
6.  클릭 **추가**, 지정 `CostService.svc` 로 **경로** 참조 되는 대시와 **확인**합니다.  
  
7.  확장의 **HTML** 에서 노드는 **도구 상자** 및 끌어서 놓기는 **입력 (단추)** 를 Default.aspx 페이지로 합니다.  
  
8.  마우스 오른쪽 단추로 클릭는 **단추** 선택 **속성**합니다.  
  
9. 변경 된 **값** 필드를 `Price for 3 Sandwiches`합니다.  
  
10. 두 번 클릭은 **단추** JavaScript 코드에 액세스할 수 있습니다.  
  
11. 내에서 다음 JavaScript 코드에 전달 된 <`script`> 요소입니다.  
  
    ```  
    function Button1_onclick() {  
    var service = new SandwichServices.CostService();  
    service.CostOfSandwiches(3, onSuccess, null, null);  
    }  
  
    function onSuccess(result){  
    alert(result);  
    }  
    ```  
  
### <a name="to-access-the-service-from-the-client"></a>클라이언트에서 서비스에 액세스하려면  
  
1.  Ctrl +F5를 사용하여 서비스 및 웹 클라이언트를 시작합니다. 클릭는 **Price for 3 Grilled Sandwiches** 예상된 출력 "3.75"를 생성 하는 단추입니다.  
  
## <a name="example"></a>예  
 이 예제에는 WCFService.svc.cs 파일에 포함된 서비스 코드 및 Default.aspx 파일에 포함된 클라이언트 코드가 있습니다.  
  
```  
//The service code contained in the CostService.svc.cs file.  
  
using System;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Activation;  
using System.ServiceModel.Web;  
  
namespace SandwichServices  
{  
    [ServiceContract(Namespace="SandwichServices")]  
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
    public class CostService  
    {  
        // Add [WebGet] attribute to use HTTP GET  
        [OperationContract]  
        public double CostOfSandwiches(int quantity)  
        {  
            return 1.25 * quantity;  
        }  
  
        // Add more operations here and mark them with [OperationContract]  
    }  
}  
//The code for hosting the service is contained in the CostService.svc file.  
  
<%@ ServiceHost Language="C#" Debug="true" Service="SandwichServices.CostService" CodeBehind="CostService.svc.cs" %>  
  
//The client code contained in the Default.aspx file.  
  
<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="SandwichServices._Default" %>  
  
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">  
  
<html >  
<head runat="server">  
    <title>Untitled Page</title>  
<script language="javascript" type="text/javascript">  
// <!CDATA[  
  
function Button1_onclick() {  
var service = new SandwichServices.CostService();  
service.CostOfSandwiches(3, onSuccess, null, null);  
}  
  
function onSuccess(result){  
alert(result);  
}  
  
// ]]>  
</script>  
</head>  
<body>  
    <form id="form1" runat="server">  
    <div>  
  
    </div>  
    <asp:ScriptManager ID="ScriptManager1" runat="server">  
        <services>  
            <asp:servicereference Path="CostService.svc" />  
        </services>  
    </asp:ScriptManager>  
    </form>  
    <p>  
        <input id="Button1" type="button" value="Price for 3 Sandwiches" onclick="return Button1_onclick()" /></p>  
</body>  
</html>  
```     
