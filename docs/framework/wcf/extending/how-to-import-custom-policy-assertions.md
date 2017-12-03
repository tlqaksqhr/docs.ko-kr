---
title: "방법: 사용자 지정 정책 어설션 가져오기"
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
ms.assetid: 1f41d787-accb-4a10-bfc6-a807671d1581
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3cc7eecbef66c3e4a80759912260b973d441a8a3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-import-custom-policy-assertions"></a><span data-ttu-id="65a1d-102">방법: 사용자 지정 정책 어설션 가져오기</span><span class="sxs-lookup"><span data-stu-id="65a1d-102">How to: Import Custom Policy Assertions</span></span>
<span data-ttu-id="65a1d-103">정책 어설션은 서비스 끝점의 기능 및 요구 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-103">Policy assertions describe the capabilities and requirements of a service endpoint.</span></span>  <span data-ttu-id="65a1d-104">클라이언트 응용 프로그램은 서비스 메타데이터에서 정책 어설션을 사용하여 서비스 끝점에 대해 서비스 계약을 사용자 지정하거나 클라이언트 바인딩을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-104">Client applications can use policy assertions in service metadata to configure the client binding or to customize the service contract for a service endpoint.</span></span>  
  
 <span data-ttu-id="65a1d-105"><xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 인터페이스를 구현하고 해당 개체를 메타데이터 시스템에 전달하거나 응용 프로그램 구성 파일에 구현 형식을 등록하면 사용자 지정 정책 어설션을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-105">Custom policy assertions are imported by implementing the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface and passing that object to the metadata system or by registering the implementation type in your application configuration file.</span></span>  <span data-ttu-id="65a1d-106"><xref:System.ServiceModel.Description.IPolicyImportExtension> 인터페이스 구현 시 기본 생성자를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-106">Implementations of the <xref:System.ServiceModel.Description.IPolicyImportExtension> interface must provide a default constructor.</span></span>  
  
### <a name="to-import-custom-policy-assertions"></a><span data-ttu-id="65a1d-107">사용자 지정 정책 어설션을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="65a1d-107">To import custom policy assertions</span></span>  
  
1.  <span data-ttu-id="65a1d-108">클래스에서 <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-108">Implement the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface on a class.</span></span> <span data-ttu-id="65a1d-109">다음 절차를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="65a1d-109">See the following procedures.</span></span>  
  
2.  <span data-ttu-id="65a1d-110">다음 중 하나를 사용하여 사용자 지정 정책 가져오기를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-110">Insert the custom policy importer either by:</span></span>  
  
3.  <span data-ttu-id="65a1d-111">구성 파일 사용</span><span class="sxs-lookup"><span data-stu-id="65a1d-111">Using a configuration file.</span></span> <span data-ttu-id="65a1d-112">다음 절차를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="65a1d-112">See the following procedures.</span></span>  
  
4.  <span data-ttu-id="65a1d-113">구성 파일을 사용 하 여 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-113">Using a configuration file with [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="65a1d-114">다음 절차를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="65a1d-114">See the following procedures.</span></span>  
  
5.  <span data-ttu-id="65a1d-115">정책 가져오기를 프로그래밍 방식으로 삽입</span><span class="sxs-lookup"><span data-stu-id="65a1d-115">Programmatically inserting the policy importer.</span></span> <span data-ttu-id="65a1d-116">다음 절차를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="65a1d-116">See the following procedures.</span></span>  
  
### <a name="to-implement-the-systemservicemodeldescriptionipolicyimportextension-interface-on-any-class"></a><span data-ttu-id="65a1d-117">클래스에서 System.ServiceModel.Description.IPolicyImportExtension 인터페이스를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="65a1d-117">To implement the System.ServiceModel.Description.IPolicyImportExtension interface on any class</span></span>  
  
1.  <span data-ttu-id="65a1d-118"><xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> 메서드에서 원하는 각 정책 주체에 대해, 이 메서드에 전달된 <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType> 개체에서 원하는 어설션 범위에 따라 적절한 메서드를 호출하여 가져올 정책 어설션을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-118">In the <xref:System.ServiceModel.Description.IPolicyImportExtension.ImportPolicy%2A?displayProperty=nameWithType> method, for each policy subject that you are interested in, find the policy assertions that you want to import by calling the appropriate method (depending upon the scope of the assertion that you want) on the <xref:System.ServiceModel.Description.PolicyConversionContext?displayProperty=nameWithType> object passed to the method.</span></span> <span data-ttu-id="65a1d-119">다음 코드 예제에서는 <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> 메서드를 사용하여 사용자 지정 정책 어설션을 찾고 컬렉션에서 이를 한 번에 제거하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-119">The following code example shows how to use the <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> method to locate the custom policy assertion and remove it from the collection in one step.</span></span> <span data-ttu-id="65a1d-120">remove 메서드를 사용하여 어설션을 찾아 제거하면 4단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-120">If you use the remove method to locate and remove the assertion, you do not have to perform step 4.</span></span>  
  
     [!code-csharp[CustomPolicySample#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/policyimporter.cs#9)]
     [!code-vb[CustomPolicySample#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/policyimporter.vb#9)]  
  
2.  <span data-ttu-id="65a1d-121">정책 어설션을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-121">Process the policy assertions.</span></span> <span data-ttu-id="65a1d-122">정책 시스템은 중첩된 정책 및 `wsp:optional`을 정규화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-122">Note that the policy system does not normalize nested policies and `wsp:optional`.</span></span> <span data-ttu-id="65a1d-123">따라서 정책 가져오기 확장 구현에서 이러한 구문을 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-123">You must process these constructs in your policy import extension implementation.</span></span>  
  
3.  <span data-ttu-id="65a1d-124">정책 어설션에 의해 지정된 기능 또는 요구 사항을 지원하는 바인딩 또는 계약에 대해 사용자 지정을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-124">Perform the customization to the binding or contract that supports the capability or requirement specified by the policy assertion.</span></span> <span data-ttu-id="65a1d-125">일반적으로 어설션은 바인딩에 특정 구성 또는 특정 바인딩 요소가 필요함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-125">Typically assertions indicate that a binding requires a particular configuration or a specific binding element.</span></span> <span data-ttu-id="65a1d-126"><xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A?displayProperty=nameWithType> 속성에 액세스하여 이러한 사항을 수정하십시오.</span><span class="sxs-lookup"><span data-stu-id="65a1d-126">Make these modifications by accessing the <xref:System.ServiceModel.Description.PolicyConversionContext.BindingElements%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="65a1d-127">다른 어설션을 사용하려면 계약을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-127">Other assertions require that you modify the contract.</span></span>  <span data-ttu-id="65a1d-128"><xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A?displayProperty=nameWithType> 속성을 사용하여 계약에 액세스하고 이를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-128">You can access and modify the contract using the <xref:System.ServiceModel.Description.PolicyConversionContext.Contract%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="65a1d-129">정책 가져오기는 동일한 바인딩 및 계약에 대해 여러 번 호출될 수 있지만 정책 대안을 가져오는 데 실패하면 다른 정책으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-129">Note that your policy importer may get called multiple times for the same binding and contract, but different policy alternatives if importing a policy alternative fails.</span></span> <span data-ttu-id="65a1d-130">사용자 코드는 이 동작에 대해 유연해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-130">Your code should be resilient to this behavior.</span></span>  
  
4.  <span data-ttu-id="65a1d-131">어설션 컬렉션에서 사용자 지정 정책 어설션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-131">Remove the custom policy assertion from the assertion collection.</span></span> <span data-ttu-id="65a1d-132">어설션을 제거하지 않으면 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서는 정책 가져오기에 실패한 것으로 간주하고 관련 바인딩을 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-132">If you do not remove the assertion [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] assumes that the policy import was unsuccessful and does not import the associated binding.</span></span> <span data-ttu-id="65a1d-133"><xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> 메서드를 사용하여 사용자 지정 정책 어설션을 찾고 컬렉션에서 이를 한 번에 제거했다면 이 단계를 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-133">If you used the <xref:System.ServiceModel.Description.PolicyAssertionCollection.Remove%2A?displayProperty=nameWithType> method to locate the custom policy assertion and remove it from the collection in one step you do not have to perform this step.</span></span>  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-a-configuration-file"></a><span data-ttu-id="65a1d-134">구성 파일을 사용하여 사용자 지정 정책 가져오기를 메타데이터 시스템에 삽입하려면</span><span class="sxs-lookup"><span data-stu-id="65a1d-134">To insert the custom policy importer into the metadata System using a configuration file</span></span>  
  
1.  <span data-ttu-id="65a1d-135">가져오기에서 형식을 추가 하는 `<extensions>` 요소 안에 [ \<policyImporters >](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) 클라이언트 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-135">Add the importer type to the `<extensions>` element inside the [\<policyImporters>](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) element in the client configuration file.</span></span>  
  
     [!code-xml[CustomPolicySample#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.exe.config#7)]   
  
2.  <span data-ttu-id="65a1d-136">클라이언트 응용 프로그램에서 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>를 사용하여 메타데이터를 확인하면 해당 가져오기가 자동으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-136">In the client application, use the <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> to resolve the metadata and the importer is invoked automatically.</span></span>  
  
     [!code-csharp[CustomPolicySample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/custompolicysample/cs/client.cs#10)]
     [!code-vb[CustomPolicySample#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/custompolicysample/vb/client.vb#10)]  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-using-svcutilexe"></a><span data-ttu-id="65a1d-137">Svcutil.exe를 사용하여 사용자 지정 정책 가져오기를 메타데이터 시스템에 삽입하려면</span><span class="sxs-lookup"><span data-stu-id="65a1d-137">To insert the custom policy importer into the metadata system using Svcutil.exe</span></span>  
  
1.  <span data-ttu-id="65a1d-138">가져오기에서 형식을 추가 하는 `<extensions>` 요소 안에 [ \<policyImporters >](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) Svcutil.exe.config 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-138">Add the importer type to the `<extensions>` element inside the [\<policyImporters>](../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md) element in the Svcutil.exe.config configuration file.</span></span> <span data-ttu-id="65a1d-139">또한 `/svcutilConfig` 옵션을 사용하여 다른 구성 파일에서 등록된 정책 가져오기 형식을 로드하도록 Svcutil.exe를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-139">You can also point Svcutil.exe to load policy importer types registered in a different configuration file by using the `/svcutilConfig` option.</span></span>  
  
2.  <span data-ttu-id="65a1d-140">사용 하 여 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 가져올 메타 데이터 및 가져오기 도구는 자동으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-140">Use [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to import the metadata and the importer is invoked automatically.</span></span>  
  
### <a name="to-insert-the-custom-policy-importer-into-the-metadata-system-programmatically"></a><span data-ttu-id="65a1d-141">프로그래밍 방식으로 사용자 지정 정책 가져오기를 메타데이터 시스템에 삽입하려면</span><span class="sxs-lookup"><span data-stu-id="65a1d-141">To insert the custom policy importer into the metadata system programmatically</span></span>  
  
1.  <span data-ttu-id="65a1d-142">메타데이터를 가져오기 전에 가져오기를 <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A?displayProperty=nameWithType> 속성(예를 들어 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>를 사용 중인 경우)에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="65a1d-142">Add the importer to the <xref:System.ServiceModel.Description.MetadataImporter.PolicyImportExtensions%2A?displayProperty=nameWithType> property (for example, if you are using the <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>) prior to importing the metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a1d-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65a1d-143">See Also</span></span>  
 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Description.MetadataResolver?displayProperty=nameWithType>  
 [<span data-ttu-id="65a1d-144">메타 데이터 시스템 확장</span><span class="sxs-lookup"><span data-stu-id="65a1d-144">Extending the Metadata System</span></span>](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)
