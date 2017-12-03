---
title: "방법: Windows Communication Foundation 서비스 계약 정의"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service contracts [WCF], defining
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
caps.latest.revision: "58"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 062167742a70307949624066b8607a37d5c7ed71
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="ec49b-102">방법: Windows Communication Foundation 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="ec49b-102">How to: Define a Windows Communication Foundation Service Contract</span></span>
<span data-ttu-id="ec49b-103">이 작업은 기본 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 응용 프로그램을 만드는 데 필요한 6가지 작업 중 첫 번째 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-103">This is the first of six tasks required to create a basic [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="ec49b-104">모든 6 가지 작업의 개요를 참조 하십시오.는 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="ec49b-105">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 만들 때 첫 번째 작업은 계약을 정의하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-105">When creating a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service, the first task is to define a service contract.</span></span> <span data-ttu-id="ec49b-106">서비스 계약은 서비스가 지원하는 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="ec49b-107">작업은 웹 서비스 메서드로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="ec49b-108">C++, C# 또는 VB(Visual Basic) 인터페이스를 정의하여 계약을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-108">Contracts are created by defining a C++, C#, or Visual Basic (VB) interface.</span></span> <span data-ttu-id="ec49b-109">인터페이스의 각 메서드는 특정 서비스 작업에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-109">Each method in the interface corresponds to a specific service operation.</span></span> <span data-ttu-id="ec49b-110">각 인터페이스에는 <xref:System.ServiceModel.ServiceContractAttribute>가 적용되어야 하고 각 작업에는 <xref:System.ServiceModel.OperationContractAttribute> 특성이 적용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-110">Each interface must have the <xref:System.ServiceModel.ServiceContractAttribute> applied to it and each operation must have the <xref:System.ServiceModel.OperationContractAttribute> attribute applied to it.</span></span> <span data-ttu-id="ec49b-111"><xref:System.ServiceModel.ServiceContractAttribute> 특성을 포함하는 인터페이스 내에 있는 메서드에 <xref:System.ServiceModel.OperationContractAttribute> 특성이 없으면 서비스에 의해 해당 메서드가 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-111">If a method within an interface that has the <xref:System.ServiceModel.ServiceContractAttribute> attribute does not have the <xref:System.ServiceModel.OperationContractAttribute> attribute, that method is not exposed by the service.</span></span>  
  
 <span data-ttu-id="ec49b-112">이 작업에 사용되는 코드는 이 절차 다음에 나오는 예제에 제공되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-112">The code used for this task is provided in the example following the procedure.</span></span>  
  
### <a name="to-define-a-service-contract"></a><span data-ttu-id="ec49b-113">서비스 계약을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="ec49b-113">To define a service contract</span></span>  
  
1.  <span data-ttu-id="ec49b-114">열기 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 에서 프로그램을 마우스 오른쪽 단추로 클릭 하 여 관리자 권한으로는 **시작** 메뉴에서 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-114">Open  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] as an administrator by right-clicking the program in the **Start** menu and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="ec49b-115">클릭 하 여 WCF 서비스 라이브러리 프로젝트를 만들기는 **파일** 메뉴에서 **새로**, **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-115">Create a WCF Service Library project by clicking the **File** menu and selecting **New**, **Project**.</span></span> <span data-ttu-id="ec49b-116">에 **새 프로젝트** 대화 상자에서 대화 상자의 왼쪽에 확장 **Visual C#** C# 프로젝트 또는 **다른 언어** 차례로 **VisualBasic** Visual Basic 프로젝트에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-116">In the **New Project** dialog, on the left-hand side of the dialog expand **Visual C#** for a C# project or **Other Languages** and then **Visual Basic** for a Visual Basic project.</span></span> <span data-ttu-id="ec49b-117">선택 된 언어에서 **WCF** 프로젝트 템플릿 목록 대화 상자 가운데에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-117">Under the language selected select **WCF** and a list of project templates will be displayed on the center section of the dialog.</span></span> <span data-ttu-id="ec49b-118">선택 **WCF 서비스 라이브러리**, 유형과 `GettingStartedLib` 에 **이름** 텍스트 상자 및 `GettingStarted` 에 **솔루션 이름** 대화 상자의 맨 아래에 텍스트 상자에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-118">Select **WCF Service Library**, and type `GettingStartedLib` in the **Name** textbox and `GettingStarted` in the **Solution name** textbox at the bottom of the dialog.</span></span>  
  
3.  <span data-ttu-id="ec49b-119">Visual Studio에서 세 파일 IService1.cs(또는 IService1.vb), Service1.cs(또는 Service1.vb) 및 App.config가 포함된 프로젝트를 만듭니다.  IService1 파일에는 기본 서비스 계약이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-119">Visual Studio will create the project which contains 3 files: IService1.cs (or IService1.vb), Service1.cs (or Service1.vb), and App.config.  The IService1 file contains a default service contract.</span></span>  <span data-ttu-id="ec49b-120">Service1 파일에는 서비스 계약의 기본 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-120">The Service1 file contains a default implementation of the service contract.</span></span> <span data-ttu-id="ec49b-121">App.config 파일에는 Visual Studio WCF 서비스 호스트가 포함된 기본 서비스를 로드하는 데 필요한 구성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-121">The App.config file contains configuration needed to load the default service with the Visual Studio WCF Service Host.</span></span> <span data-ttu-id="ec49b-122">WCF 서비스 호스트 도구에 대 한 자세한 내용은 참조 [WCF 서비스 호스트 (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="ec49b-122">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span></span>  
  
4.  <span data-ttu-id="ec49b-123">IService1.cs 또는 IService1.vb 파일을 열고 네임스페이스 선언 안의 코드를 삭제하고 네임스페이스 선언은 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-123">Open the IService1.cs or IService1.vb file and delete the code within the namespace declaration leaving the namespace declaration.</span></span> <span data-ttu-id="ec49b-124">다음 코드와 같이 네임스페이스 선언 내에 `ICalculator`라는 새 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-124">Inside the namespace declaration define a new interface called `ICalculator` as shown in the code below.</span></span>  
  
    ```  
    // IService.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Runtime.Serialization;  
    using System.ServiceModel;  
    using System.Text;  
  
    namespace GettingStartedLib  
    {  
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
            public interface ICalculator  
            {  
                [OperationContract]  
                double Add(double n1, double n2);  
                [OperationContract]  
                double Subtract(double n1, double n2);  
                [OperationContract]  
                double Multiply(double n1, double n2);  
                [OperationContract]  
                double Divide(double n1, double n2);  
            }  
    }  
    ```  
  
    ```  
    ‘IService.vb  
    Imports System  
    Imports System.ServiceModel  
  
    Namespace GettingStartedLib  
  
        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _  
        Public Interface ICalculator  
  
            <OperationContract()> _  
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double  
        End Interface  
    End Namespace  
    ```  
  
     <span data-ttu-id="ec49b-125">이 계약은 온라인 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-125">This contract defines an online calculator.</span></span> <span data-ttu-id="ec49b-126">`ICalculator` 인터페이스에는 <xref:System.ServiceModel.ServiceContractAttribute> 특성이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-126">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="ec49b-127">이 특성은 계약 이름을 명확히 나타내는 데 사용하는 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-127">This attribute defines a namespace that is used to disambiguate the contract name.</span></span> <span data-ttu-id="ec49b-128">각 계산기 연산에는 <xref:System.ServiceModel.OperationContractAttribute> 특성이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-128">Each calculator operation is marked with the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ec49b-129">특성을 사용하여 인터페이스, 멤버 또는 클래스에 주석을 달 때 특성 이름에서 "특성" 부분을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-129">When using attributes to annotate an interface, member, or class, you can drop the "Attribute" part from the attribute name.</span></span> <span data-ttu-id="ec49b-130">따라서 <xref:System.ServiceModel.ServiceContractAttribute>는 `[ServiceContract]`(C#의 경우) 또는 `<ServiceContract>`(Visual Basic의 경우)가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec49b-130">So <xref:System.ServiceModel.ServiceContractAttribute> becomes `[ServiceContract]` in C#, or `<ServiceContract>` in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec49b-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec49b-131">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="ec49b-132">방법: 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="ec49b-132">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [<span data-ttu-id="ec49b-133">시작</span><span class="sxs-lookup"><span data-stu-id="ec49b-133">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="ec49b-134">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="ec49b-134">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
