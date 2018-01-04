---
title: "WorkflowServiceHost에서 Side-by-side 버전 관리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 60887eed-df40-4412-b812-41e1dd329d15
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: db8f79fcdc1398b891933f5fef9f07410e5de11e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="side-by-side-versioning-in-workflowservicehost"></a><span data-ttu-id="d4d73-102">WorkflowServiceHost에서 Side-by-side 버전 관리</span><span class="sxs-lookup"><span data-stu-id="d4d73-102">Side by Side Versioning in WorkflowServiceHost</span></span>
<span data-ttu-id="d4d73-103"><xref:System.ServiceModel.Activities.WorkflowServiceHost>에 소개된 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] side-by-side 버전 관리는 단일 끝점에서 여러 버전의 워크플로 서비스를 호스팅하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-103">The <xref:System.ServiceModel.Activities.WorkflowServiceHost> side-by-side versioning introduced in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] provides the capability to host multiple versions of a workflow service on a single endpoint.</span></span> <span data-ttu-id="d4d73-104">제공된 side-by-side 기능을 사용하여 워크플로 서비스를 구성할 수 있습니다. 그러면 기존 정의를 사용하여 실행 중인 인스턴스를 완료하는 동시에, 새 워크플로 정의를 사용하여 워크플로 서비스의 새 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-104">The side-by-side functionality provided allows a workflow service to be configured so that new instances of the workflow service are created using the new workflow definition, while running instances complete using the existing definition.</span></span> <span data-ttu-id="d4d73-105">이 항목에서는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>를 사용하는 워크플로 서비스 side-by-side 실행에 대해 대략적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-105">This topic provides an overview of workflow service side-by-side execution using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4d73-106">샘플을 다운로드 하 고 워크플로 서비스-side-by-side 버전 관리 연습 비디오를 시청 참조 [하려면 Xamlx 워크플로 서비스를 사용한 Side-by-side 버전 관리](http://go.microsoft.com/fwlink/?LinkId=393746)합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-106">To download a sample and watch a video walkthrough of workflow service side-by-side versioning, see [Side by Side Versioning with a Web-Hosted Xamlx Workflow Service](http://go.microsoft.com/fwlink/?LinkId=393746).</span></span>  
  
## <a name="hosting-multiple-versions-in-a-workflow-service"></a><span data-ttu-id="d4d73-107">워크플로 서비스에서 여러 버전 호스팅</span><span class="sxs-lookup"><span data-stu-id="d4d73-107">Hosting Multiple Versions in a Workflow Service</span></span>  
 <span data-ttu-id="d4d73-108"><xref:System.ServiceModel.Activities.WorkflowServiceHost>에는 여러 버전의 워크플로를 동시에 실행(Side-by-Side 실행)하도록 구성할 수 있는 두 가지 속성, <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> 및 <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-108"><xref:System.ServiceModel.Activities.WorkflowServiceHost> contains two properties that can be configured to allow multiple versions of a workflow to execute side-by-side: <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> and <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span> <span data-ttu-id="d4d73-109"><xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A>에는 지원되는 워크플로 서비스 버전이 포함되어 있으며, <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>를 사용하여 각 워크플로 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-109"><xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> contains the supported versions of the workflow service, and <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is used to uniquely identify each workflow service.</span></span> <span data-ttu-id="d4d73-110">이 작업은 <xref:System.Activities.WorkflowIdentity>를 워크플로 서비스와 연결하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-110">This is done by associating a <xref:System.Activities.WorkflowIdentity> with the workflow service.</span></span> <span data-ttu-id="d4d73-111"><xref:System.Activities.WorkflowIdentity>에는 세 가지 식별 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-111">A <xref:System.Activities.WorkflowIdentity> contains three identifying pieces of information.</span></span> <span data-ttu-id="d4d73-112">필수 요소인 <xref:System.Activities.WorkflowIdentity.Name%2A> 및 <xref:System.Activities.WorkflowIdentity.Version%2A>에는 이름과 <xref:System.Version>이 포함되며, 선택적인 <xref:System.Activities.WorkflowIdentity.Package%2A>는 어셈블리 이름 등의 정보나 원하는 다른 정보를 포함하는 추가 문자열을 지정하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-112"><xref:System.Activities.WorkflowIdentity.Name%2A> and <xref:System.Activities.WorkflowIdentity.Version%2A> contain a name and a <xref:System.Version> and are required, and <xref:System.Activities.WorkflowIdentity.Package%2A> is optional and can be used to specify an additional string containing information such as assembly name or other desired information.</span></span> <span data-ttu-id="d4d73-113"><xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> 컬렉션에 포함된 각 워크플로 서비스의 <xref:System.Activities.WorkflowIdentity>는 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-113">Each workflow service contained in the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection must have a unique <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="d4d73-114">세 개의 속성 중 하나라도 다른 <xref:System.Activities.WorkflowIdentity>와 다르면 <xref:System.Activities.WorkflowIdentity>가 고유한 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-114">A <xref:System.Activities.WorkflowIdentity> is unique if any of its three properties are different from another <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="d4d73-115">A `null` <xref:System.Activities.WorkflowIdentity> 허용 가능한 값에 대 한 <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, 워크플로 서비스의 이전 버전을 하나만 있을 수는 `null` <xref:System.Activities.WorkflowIdentity>합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-115">A `null` <xref:System.Activities.WorkflowIdentity> is an allowable value for <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, but only one previous version of a workflow service may have a `null` <xref:System.Activities.WorkflowIdentity>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d4d73-116"><xref:System.Activities.WorkflowIdentity>에는 어떠한 PII(개인적으로 식별할 수 있는 정보)도 포함해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-116">A <xref:System.Activities.WorkflowIdentity> should not contain any personally identifiable information (PII).</span></span> <span data-ttu-id="d4d73-117"><xref:System.Activities.WorkflowIdentity>는 <xref:System.Activities.WorkflowIdentity.Name%2A>(<xref:System.String>), <xref:System.Activities.WorkflowIdentity.Version%2A>(<xref:System.Version>), 및 <xref:System.Activities.WorkflowIdentity.Package%2A>(<xref:System.String>)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-117"><xref:System.Activities.WorkflowIdentity> is composed of three parts: a <xref:System.Activities.WorkflowIdentity.Name%2A> (<xref:System.String>), a <xref:System.Activities.WorkflowIdentity.Version%2A> (<xref:System.Version>), and a <xref:System.Activities.WorkflowIdentity.Package%2A> (<xref:System.String>).</span></span> <span data-ttu-id="d4d73-118">인스턴스를 만드는 데 사용되는 <xref:System.Activities.WorkflowIdentity>에 대한 정보는 활동 수명 주기의 여러 시점에 런타임에 의해 구성된 추적 서비스로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-118">Information about the <xref:System.Activities.WorkflowIdentity> used to create an instance is emitted to any configured tracking services at several different points of the activity life-cycle by the runtime.</span></span> <span data-ttu-id="d4d73-119">WF 추적 기능에는 중요한 사용자 데이터인 PII를 숨기는 메커니즘이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-119">WF Tracking does not have any mechanism to hide PII (sensitive user data).</span></span> <span data-ttu-id="d4d73-120">따라서 <xref:System.Activities.WorkflowIdentity> 인스턴스는 런타임에 의해 추적 레코드에 내보내져 추적 레코드를 볼 수 있는 권한이 있는 사람에게 표시될 수 있기 때문에 이 인스턴스에 PII 데이터가 포함되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-120">Therefore, a <xref:System.Activities.WorkflowIdentity> instance should not contain any PII data as it will be emitted by the runtime in tracking records and may be visible to anyone with access to view the tracking records.</span></span>  
  
### <a name="rules-for-hosting-multiple-versions-of-a-workflow-service"></a><span data-ttu-id="d4d73-121">워크플로 서비스의 여러 버전 호스팅에 대한 규칙</span><span class="sxs-lookup"><span data-stu-id="d4d73-121">Rules for Hosting Multiple Versions of a Workflow Service</span></span>  
 <span data-ttu-id="d4d73-122">사용자가 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에 추가 버전을 추가할 경우 동일한 끝점 및 설명 집합을 사용하여 워크플로 서비스를 호스팅하려면 몇 가지 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-122">When a user adds an additional version to the <xref:System.ServiceModel.Activities.WorkflowServiceHost>, there are several conditions that must be met in order for a workflow service to be hosted with the same set of endpoints and description.</span></span> <span data-ttu-id="d4d73-123">추가 버전 중 하나라도 이러한 조건을 충족하지 못하면 <xref:System.ServiceModel.Activities.WorkflowServiceHost>이 호출될 때 `Open`에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-123">If any of the additional versions fail to meet these conditions, the <xref:System.ServiceModel.Activities.WorkflowServiceHost> throws an exception when `Open` is called.</span></span> <span data-ttu-id="d4d73-124">호스트에 추가 버전으로 제공된 각 워크플로 정의는 다음 요구사항을 충족해야 합니다(주 버전은 호스트 생성자에 제공된 워크플로 서비스 정의임).</span><span class="sxs-lookup"><span data-stu-id="d4d73-124">Each workflow definition provided to the host as an additional version must meet the following requirements (where the primary version is the workflow service definition that is provided to the host constructor).</span></span> <span data-ttu-id="d4d73-125">추가 워크플로 버전은 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-125">The additional workflow version must:</span></span>  
  
-   <span data-ttu-id="d4d73-126">워크플로 서비스의 주 버전과 <xref:System.ServiceModel.Activities.WorkflowService.Name%2A>이 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-126">Have the same the <xref:System.ServiceModel.Activities.WorkflowService.Name%2A> as the primary version of the workflow service.</span></span>  
  
-   <span data-ttu-id="d4d73-127"><xref:System.ServiceModel.Activities.Receive>에 주 버전에 없는 <xref:System.ServiceModel.Activities.SendReply> 또는 <xref:System.ServiceModel.Activities.WorkflowService.Body%2A> 작업이 없어야 하며 작업 계약과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-127">Must not have any <xref:System.ServiceModel.Activities.Receive> or <xref:System.ServiceModel.Activities.SendReply> activities in its <xref:System.ServiceModel.Activities.WorkflowService.Body%2A> that are not in the primary version, and they must match the operation contract.</span></span>  
  
-   <span data-ttu-id="d4d73-128">고유한 <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-128">Have a unique <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span> <span data-ttu-id="d4d73-129">워크플로 정의 하나만 있을 수는 `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-129">One and only one workflow definition may have a `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span>  
  
 <span data-ttu-id="d4d73-130">일부 변경 내용은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-130">Some changes are permitted.</span></span> <span data-ttu-id="d4d73-131">다음 항목은 버전간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-131">The following items may be different between the versions:</span></span>  
  
-   <span data-ttu-id="d4d73-132"><xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>는 주 버전과 Name 및 Package가 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-132">The <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> may have a different Name and Package than the primary version.</span></span>  
  
-   <span data-ttu-id="d4d73-133"><xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> 값은 주 버전과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-133">The <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> value may be different than the primary version.</span></span>  
  
-   <span data-ttu-id="d4d73-134"><xref:System.ServiceModel.Activities.WorkflowService.ConfigurationName%2A>은 주 버전과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-134">The <xref:System.ServiceModel.Activities.WorkflowService.ConfigurationName%2A> may be different than the primary version.</span></span>  
  
-   <span data-ttu-id="d4d73-135"><xref:System.ServiceModel.Activities.WorkflowService.ImplementedContracts%2A>은 주 버전과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-135">The <xref:System.ServiceModel.Activities.WorkflowService.ImplementedContracts%2A> may be different than the primary version.</span></span>  
  
### <a name="configuring-the-definitionidentity"></a><span data-ttu-id="d4d73-136">DefinitionIdentity 구성</span><span class="sxs-lookup"><span data-stu-id="d4d73-136">Configuring the DefinitionIdentity</span></span>  
 <span data-ttu-id="d4d73-137">워크플로 디자이너를 사용 하 여 워크플로 서비스를 만들 때의 <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> 사용 하 여 설정 되는 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="d4d73-137">When a workflow service is created using the workflow designer, the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is set using the **Properties** window.</span></span> <span data-ttu-id="d4d73-138">워크플로 서비스를 선택 하 고 선택 하려면 디자이너에서 서비스의 루트 활동 밖을 클릭 **속성 창** 에서 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="d4d73-138">Click outside of the service’s root activity in the designer to select the workflow service, and choose **Properties Window** from the **View** menu.</span></span> <span data-ttu-id="d4d73-139">선택 **WorkflowIdentity** 옆에 나타나는 드롭다운 목록에서는 **DefinitionIdentity** 속성을 다음를 확장 하 고 원하는 지정 <xref:System.Activities.WorkflowIdentity> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-139">Select **WorkflowIdentity** from the drop-down list that appears beside the **DefinitionIdentity** property, and then expand and specify the desired <xref:System.Activities.WorkflowIdentity> properties.</span></span> <span data-ttu-id="d4d73-140">다음 예제에서는 <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> 구성 된는 <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` 및 <xref:System.Activities.WorkflowIdentity.Version%2A> 의 `1.0.0.0`합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-140">In the following example the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is configured with the <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` and a <xref:System.Activities.WorkflowIdentity.Version%2A> of `1.0.0.0`.</span></span> <span data-ttu-id="d4d73-141"><xref:System.Activities.WorkflowIdentity.Package%2A>는 선택 사항이며 이 예에서는 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-141"><xref:System.Activities.WorkflowIdentity.Package%2A> is optional and in this example is `null`.</span></span>  
  
 <span data-ttu-id="d4d73-142">![DefinitionIdentity](../../../../docs/framework/wcf/feature-details/media/workflowservicedefinitionidentityv1.bmp "WorkflowServiceDefinitionIdentityv1")</span><span class="sxs-lookup"><span data-stu-id="d4d73-142">![DefinitionIdentity](../../../../docs/framework/wcf/feature-details/media/workflowservicedefinitionidentityv1.bmp "WorkflowServiceDefinitionIdentityv1")</span></span>  
  
 <span data-ttu-id="d4d73-143">워크플로 서비스가 자체 호스팅된 경우 워크플로 서비스가 생성되면 <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-143">When a workflow service is self-hosted, the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is configured when the workflow service is constructed.</span></span> <span data-ttu-id="d4d73-144">다음 예제에서는 <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> 앞의 예제와 동일한 값으로 구성 됩니다는 <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` 및 <xref:System.Activities.WorkflowIdentity.Name%2A> 의 `1.0.0.0`합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-144">In the following example, the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is configured with the same values as the previous example, with the <xref:System.Activities.WorkflowIdentity.Name%2A> `MortgageWorkflow` and a <xref:System.Activities.WorkflowIdentity.Name%2A> of `1.0.0.0`.</span></span>  
  
```csharp  
WorkflowService service = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflow(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    }  
};  
```  
  
```vb  
Dim service As New WorkflowService  
With service  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflow  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(1, 0, 0, 0) _  
    }  
End With  
```  
  
 <span data-ttu-id="d4d73-145">A <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> 은 워크플로 서비스의 버전을 하나만 있을 수 있지만 필요 하지는 **null**<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-145">A <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> is not required, although only one version of the workflow service may have a **null**<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4d73-146">이는 최초에 <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>를 구성하지 않고 서비스를 구성한 다음 업데이트된 버전을 만들 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-146">This is useful if the service was deployed initially without a <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> configured, and then an updated version is created.</span></span>  
  
### <a name="adding-a-new-version-to-a-web-hosted-workflow-service"></a><span data-ttu-id="d4d73-147">웹 호스팅된 워크플로 서비스에 새 버전 추가</span><span class="sxs-lookup"><span data-stu-id="d4d73-147">Adding a New Version to a Web-hosted Workflow Service</span></span>  
 <span data-ttu-id="d4d73-148">웹 호스팅된 서비스에 새 버전의 워크플로 서비스를 구성할 때 첫 번째 단계는 서비스 파일과 이름이 동일한 `App_Code` 폴더에 새 폴더를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-148">The first step in configuring a new version of a workflow service in a web-hosted service is to create a new folder in the `App_Code` folder that has the same name as the service file.</span></span> <span data-ttu-id="d4d73-149">서비스의 `xamlx` 파일 이름이 `MortgageWorkflow.xamlx`인 경우 폴더 이름을 `MortgageWorkflow`로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-149">If the service’s `xamlx` file is named `MortgageWorkflow.xamlx`, then the folder must be named `MortgageWorkflow`.</span></span> <span data-ttu-id="d4d73-150">원본 서비스의 `xamlx` 파일의 사본을 이 폴더에 넣은 다음 `MortgageWorkflowV1.xamlx`와 같은 새 이름으로 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-150">Place a copy of the original service’s `xamlx` file into this folder and rename it to a new name, such as `MortgageWorkflowV1.xamlx`.</span></span> <span data-ttu-id="d4d73-151">기본 서비스를 원하는 대로 변경하고 <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>를 업데이트한 다음 서비스를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-151">Make the desired changes to the primary service, update its <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, and then deploy the service.</span></span> <span data-ttu-id="d4d73-152">다음 예제에서는 <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>의 <xref:System.Activities.WorkflowIdentity.Name%2A> 및 `MortageWorkflow`의 <xref:System.Activities.WorkflowIdentity.Version%2A>을 사용하여 `2.0.0.0`를 업데이트하였습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-152">In the following example the <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> has been updated with a <xref:System.Activities.WorkflowIdentity.Name%2A> of `MortageWorkflow` and a <xref:System.Activities.WorkflowIdentity.Version%2A> of `2.0.0.0`.</span></span>  
  
 <span data-ttu-id="d4d73-153">![DefinitionIdentity](../../../../docs/framework/wcf/feature-details/media/workflowservicedefinitionidentityv2.bmp "WorkflowServiceDefinitionIdentityv2")</span><span class="sxs-lookup"><span data-stu-id="d4d73-153">![DefinitionIdentity](../../../../docs/framework/wcf/feature-details/media/workflowservicedefinitionidentityv2.bmp "WorkflowServiceDefinitionIdentityv2")</span></span>  
  
 <span data-ttu-id="d4d73-154">서비스가 다시 시작되면 이전 버전이 지정된 <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> 하위 폴더에 위치하므로 `App_Code` 컬렉션에 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-154">When the service restarts, the previous version will automatically be added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection because it is located in the designated `App_Code` subfolder.</span></span> <span data-ttu-id="d4d73-155">경우에 워크플로 서비스의 기본 버전에는 `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> 이전 버전에 추가 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-155">Note that if the primary version of the workflow service has a `null` <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> the previous versions will not be added.</span></span> <span data-ttu-id="d4d73-156">한 버전에 `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>가 있을 수는 있지만, 복수 버전이 있는 경우 `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>가 포함된 기본 버전은 허용되지 않습니다. 그렇지 않으면 이전 버전이 <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> 컬렉션에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-156">One version may have a `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>, but if there are multiple versions the primary version must not be the one with the `null`<xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> or else the previous versions will not be added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection.</span></span>  
  
### <a name="adding-a-new-version-to-a-self-hosted-workflow-service"></a><span data-ttu-id="d4d73-157">자체 호스팅된 워크플로 서비스에 새 버전 추가</span><span class="sxs-lookup"><span data-stu-id="d4d73-157">Adding a New Version to a Self-hosted Workflow Service</span></span>  
 <span data-ttu-id="d4d73-158">자체 호스팅된 워크플로 서비스에 새 버전을 추가하면 워크플로 서비스의 기본 버전으로 <xref:System.ServiceModel.Activities.WorkflowServiceHost>가 구성되며, 이전 버전은 <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> 컬렉션에 명시적으로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-158">When adding a new version to a self-hosted workflow service, the <xref:System.ServiceModel.Activities.WorkflowServiceHost> is configured with the primary version of the workflow service, and previous versions must be explicitly added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection.</span></span> <span data-ttu-id="d4d73-159">다음 예제에서는 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 워크플로 정의를 사용하는 기본 워크플로 서비스를 사용하여 `MortgageWorkflowV2`를 구성하고 `MortgageWorkflowV1` 워크플로 정의를 사용하여 구성된 워크플로 서비스가 <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> 컬렉션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-159">In the following example, a <xref:System.ServiceModel.Activities.WorkflowServiceHost> is configured with a primary workflow service that uses a `MortgageWorkflowV2` workflow definition, and a workflow service configured with a `MortgageWorkflowV1` workflow definition is added to the <xref:System.ServiceModel.Activities.WorkflowServiceHost.SupportedVersions%2A> collection.</span></span> <span data-ttu-id="d4d73-160">각 워크플로 서비스는 워크플로 정의 버전을 나타내는 고유한 <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A>를 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d73-160">Each workflow service is configured with a unique <xref:System.ServiceModel.Activities.WorkflowService.DefinitionIdentity%2A> that reflects the version of the workflow definition.</span></span>  
  
```csharp  
// Create the primary version of the workflow service.  
WorkflowService serviceV2 = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflowV2(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(2, 0, 0, 0)  
    }  
};  
  
// Configure the WorkflowServiceHost with the current version  
// of the workflow service. This code requires Administrator  
// privileges to function correctly. If running from Visual  
// Studio, Visual Studio must be run with Administrator privileges.  
WorkflowServiceHost host = new WorkflowServiceHost(serviceV2,   
    new Uri("http://localhost:8080/MortgageWorkflowService"));  
  
// Create the previous version of the workflow service.  
WorkflowService serviceV1 = new WorkflowService  
{  
    Name = "MortgageWorkflowService",  
    Body = new MortgageWorkflowV1(),  
    DefinitionIdentity = new WorkflowIdentity  
    {  
        Name = "MortgageWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    }  
};  
  
// Add the previous version of the service to the SupportedVersions collection.  
host.SupportedVersions.Add(serviceV1);  
```  
  
```vb  
'Create the primary version of the workflow service  
Dim serviceV2 As New WorkflowService  
With serviceV2  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflowV2  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(2, 0, 0, 0) _  
    }  
End With  
  
'Configure the WorkflowServiceHost with the current version  
'of the workflow service. This code requires Administrator  
'privileges to function correctly. If running from Visual  
'Studio, Visual Studio must be run with Administrator privileges.  
  
Dim host As New WorkflowServiceHost(serviceV2, _  
    New Uri("http://localhost:8080/MortgageWorkflowService"))  
  
'Create the previous version of the workflow service.  
Dim serviceV1 As New WorkflowService  
With serviceV1  
    .Name = "MortgageWorkflowService"  
    .Body = New MortgageWorkflowV1  
    .DefinitionIdentity = New WorkflowIdentity With _  
    { _  
        .Name = "MortgageWorkflow", _  
        .Version = New Version(1, 0, 0, 0) _  
    }  
End With  
  
'Add the previous version of the service to the SupportedVersions collection.  
host.SupportedVersions.Add(serviceV1)  
```
