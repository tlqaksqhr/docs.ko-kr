---
title: '방법: AJAX 사용 WCF 서비스 및 해당 서비스에 액세스하는 ASP.NET 클라이언트 만들기'
ms.date: 03/30/2017
ms.assetid: 95012df8-2a66-420d-944a-8afab261013e
ms.openlocfilehash: 58971d11ab76112627dd81d53381236932268e25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490632"
---
# <a name="how-to-create-an-ajax-enabled-wcf-service-and-an-aspnet-client-that-accesses-the-service"></a><span data-ttu-id="91b3f-102">방법: AJAX 사용 WCF 서비스 및 해당 서비스에 액세스하는 ASP.NET 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="91b3f-102">How to: Create an AJAX-Enabled WCF Service and an ASP.NET Client that Accesses the Service</span></span>
<span data-ttu-id="91b3f-103">이 항목에는 AJAX 사용 WCF Windows Communication Foundation () 서비스 및 서비스에 액세스 하는 ASP.NET 클라이언트를 만들려면 Visual Studio 2008을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-103">This topic shows how to use Visual Studio 2008 to create an AJAX-enabled Windows Communication Foundation (WCF) service and an ASP.NET client that accesses the service.</span></span> <span data-ttu-id="91b3f-104">서비스 및 클라이언트 코드의 경우 절차 단원에서 서비스 및 클라이언트를 만드는 단계에 대해 설명한 다음 예제 단원에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-104">The code for the service and for the client are provided in the Example section after the steps for creating them are described in the Procedures section.</span></span>  
  
### <a name="to-create-the-aspnet-client-application"></a><span data-ttu-id="91b3f-105">ASP.NET 클라이언트 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="91b3f-105">To create the ASP.NET client application</span></span>  
  
1.  <span data-ttu-id="91b3f-106">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-106">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="91b3f-107">**파일** 메뉴 선택 **새로**, 다음 **프로젝트**, 다음 **웹**를 선택한 후 **ASP.NET 웹 응용 프로그램**.</span><span class="sxs-lookup"><span data-stu-id="91b3f-107">From the **File** menu, select **New**, then **Project**, then **Web**, and then select **ASP.NET Web Application**.</span></span>  
  
3.  <span data-ttu-id="91b3f-108">프로젝트 이름을 `SandwichServices` 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-108">Name the Project `SandwichServices` and click **OK**.</span></span>  
  
### <a name="to-create-the-wcf-ajax-enabled-service"></a><span data-ttu-id="91b3f-109">WCF AJAX 사용 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="91b3f-109">To create the WCF AJAX-enabled service</span></span>  
  
1.  <span data-ttu-id="91b3f-110">마우스 오른쪽 단추로 클릭는 `SandwichServices` 프로젝트에 **솔루션 탐색기** 창과 선택 **추가**, 다음 **새 항목**, 차례로 **AJAX 사용 WCF 서비스** .</span><span class="sxs-lookup"><span data-stu-id="91b3f-110">Right-click the `SandwichServices` project in the **Solution Explorer** window and select **Add**, then **New Item**, and then **AJAX-enabled WCF Service**.</span></span>  
  
2.  <span data-ttu-id="91b3f-111">서비스 이름을 `CostService` 에 **이름** 상자 한 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-111">Name the service `CostService` in the **Name** box and click **Add**.</span></span>  
  
3.  <span data-ttu-id="91b3f-112">CostService.svc.cs 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-112">Open the CostService.svc.cs file.</span></span>  
  
4.  <span data-ttu-id="91b3f-113">지정 된 `Namespace` 에 대 한 <xref:System.ServiceModel.ServiceContractAttribute> 으로 `SandwichService`:</span><span class="sxs-lookup"><span data-stu-id="91b3f-113">Specify the `Namespace` for <xref:System.ServiceModel.ServiceContractAttribute> as `SandwichService`:</span></span>  
  
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
  
5.  <span data-ttu-id="91b3f-114">서비스에서 작업을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-114">Implement the operations in the service.</span></span> <span data-ttu-id="91b3f-115">각 작업에 <xref:System.ServiceModel.OperationContractAttribute>를 추가하여 계약의 일부라는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-115">Add the <xref:System.ServiceModel.OperationContractAttribute> to each of the operations to indicate that they are part of the contract.</span></span> <span data-ttu-id="91b3f-116">다음 예제에서는 지정된 샌드위치 개수에 대한 비용을 반환하는 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-116">The following example implements a method that returns the cost of a given quantity of sandwiches.</span></span>  
  
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
  
### <a name="to-configure-the-client-to-access-the-service"></a><span data-ttu-id="91b3f-117">서비스에 액세스하도록 클라이언트를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="91b3f-117">To configure the client to access the service</span></span>  
  
1.  <span data-ttu-id="91b3f-118">Default.aspx 페이지를 열고 선택 된 **디자인** 보기.</span><span class="sxs-lookup"><span data-stu-id="91b3f-118">Open the Default.aspx page and select the **Design** view.</span></span>  
  
2.  <span data-ttu-id="91b3f-119">**보기** 메뉴 선택 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-119">From the **View** menu, select **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="91b3f-120">확장 하 고는 **AJAX 확장** 노드 및 끌어서 놓기는 **ScriptManager** Default.aspx 페이지에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-120">Expand the **AJAX Extensions** node and drag and drop a **ScriptManager** on to the Default.aspx page.</span></span>  
  
4.  <span data-ttu-id="91b3f-121">마우스 오른쪽 단추로 클릭는 **ScriptManager** 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-121">Right-click the **ScriptManager** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="91b3f-122">확장 된 **서비스** 컬렉션에는 **속성** 창을 엽니다는 **ServiceReference 컬렉션 편집기** 창.</span><span class="sxs-lookup"><span data-stu-id="91b3f-122">Expand the **Services** collection in the **Properties** window to open up the **ServiceReference Collection Editor** window.</span></span>  
  
6.  <span data-ttu-id="91b3f-123">클릭 **추가**, 지정 `CostService.svc` 로 **경로** 참조 되는 대시와 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-123">Click **Add**, specify `CostService.svc` as the **Path** referenced, and click **OK**.</span></span>  
  
7.  <span data-ttu-id="91b3f-124">확장의 **HTML** 에서 노드는 **도구 상자** 및 끌어서 놓기는 **입력 (단추)** 를 Default.aspx 페이지로 합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-124">Expand the **HTML** node in the **Toolbox** and drag and drop an **Input (Button)** on to the Default.aspx page.</span></span>  
  
8.  <span data-ttu-id="91b3f-125">마우스 오른쪽 단추로 클릭는 **단추** 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-125">Right-click the **Button** and select **Properties**.</span></span>  
  
9. <span data-ttu-id="91b3f-126">변경 된 **값** 필드를 `Price for 3 Sandwiches`합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-126">Change the **Value** field to `Price for 3 Sandwiches`.</span></span>  
  
10. <span data-ttu-id="91b3f-127">두 번 클릭은 **단추** JavaScript 코드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-127">Double-click the **Button** to access the JavaScript code.</span></span>  
  
11. <span data-ttu-id="91b3f-128">내에서 다음 JavaScript 코드에 전달 된 <`script`> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-128">Pass in the following JavaScript code within the <`script`> element.</span></span>  
  
    ```  
    function Button1_onclick() {  
    var service = new SandwichServices.CostService();  
    service.CostOfSandwiches(3, onSuccess, null, null);  
    }  
  
    function onSuccess(result){  
    alert(result);  
    }  
    ```  
  
### <a name="to-access-the-service-from-the-client"></a><span data-ttu-id="91b3f-129">클라이언트에서 서비스에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="91b3f-129">To access the service from the client</span></span>  
  
1.  <span data-ttu-id="91b3f-130">Ctrl +F5를 사용하여 서비스 및 웹 클라이언트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-130">Use Ctrl +F5 to launch the service and the Web client.</span></span> <span data-ttu-id="91b3f-131">클릭는 **Price for 3 Grilled Sandwiches** 예상된 출력 "3.75"를 생성 하는 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-131">Click the **Price for 3 Grilled Sandwiches** button to generate the expected output of "3.75".</span></span>  
  
## <a name="example"></a><span data-ttu-id="91b3f-132">예제</span><span class="sxs-lookup"><span data-stu-id="91b3f-132">Example</span></span>  
 <span data-ttu-id="91b3f-133">이 예제에는 WCFService.svc.cs 파일에 포함된 서비스 코드 및 Default.aspx 파일에 포함된 클라이언트 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91b3f-133">This example contains the service code contained in the WCFService.svc.cs file and the client code contained in the Default.aspx file.</span></span>  
  
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
