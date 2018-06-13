---
title: 구성 파일을 사용하여 서비스 구성
ms.date: 03/30/2017
helpviewer_keywords:
- configuring services [WCF]
ms.assetid: c9c8cd32-2c9d-4541-ad0d-16dff6bd2a00
ms.openlocfilehash: 19ba0e585dfdd2ee47781b04a3d1a5bbdba60371
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807435"
---
# <a name="configuring-services-using-configuration-files"></a><span data-ttu-id="6c5ce-102">구성 파일을 사용하여 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="6c5ce-102">Configuring Services Using Configuration Files</span></span>
<span data-ttu-id="6c5ce-103">구성 파일을 사용 하 여 Windows Communication Foundation (WCF) 서비스를 구성 하면 끝점을 제공 하 고 디자인 타임 대신 배포 지점에서 서비스 동작 데이터.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-103">Configuring a Windows Communication Foundation (WCF) service with a configuration file gives you the flexibility of providing endpoint and service behavior data at the point of deployment instead of at design time.</span></span> <span data-ttu-id="6c5ce-104">이 항목에서는 사용할 수 있는 기본 기술에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-104">This topic outlines the primary techniques available.</span></span>  
  
 <span data-ttu-id="6c5ce-105">WCF 서비스를 사용 하 여 구성할 수는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 기술을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-105">A WCF service is configurable using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration technology.</span></span> <span data-ttu-id="6c5ce-106">가장 일반적으로 XML 요소는 WCF 서비스를 호스트 하는 인터넷 정보 서비스 (IIS) 사이트의 Web.config 파일에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-106">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="6c5ce-107">이 요소를 사용하여 끝점 주소(서비스와의 통신에 사용되는 실제 주소)와 같은 세부 사항을 컴퓨터별로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-107">The elements allow you to change details such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span> <span data-ttu-id="6c5ce-108">또한 WCF 서비스에 대 한 가장 기본적인 기능을 빠르게 선택할 수 있도록 하는 여러 시스템 제공 요소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-108">In addition, WCF includes several system-provided elements that allow you to quickly select the most basic features for a service.</span></span> <span data-ttu-id="6c5ce-109">부터는 [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF WCF 구성 요구 사항을 간소화 하는 새로운 기본 구성 모델이 함께 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="6c5ce-110">특정 서비스에 대 한 모든 WCF 구성 정보를 제공 하지 않으면 런타임이 일부 표준 끝점 및 기본 바인딩/동작으로 서비스 자동으로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with some standard endpoints and default binding/behavior.</span></span> <span data-ttu-id="6c5ce-111">실제로 구성 작성은 주요 WCF 응용 프로그램 프로그래밍의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-111">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
 <span data-ttu-id="6c5ce-112">자세한 내용은 참조 [서비스에 대 한 바인딩을 구성](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-112">For more information, see [Configuring Bindings for Services](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md).</span></span> <span data-ttu-id="6c5ce-113">가장의 목록이 요소에 일반적으로 사용 되는 경우 참조 [시스템 제공 바인딩](../../../docs/framework/wcf/system-provided-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-113">For a list of of the most commonly used elements, see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md).</span></span> <span data-ttu-id="6c5ce-114">기본 끝점, 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-114">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6c5ce-115">서로 다른 두 버전의 서비스가 배포되는 병렬 배포 시나리오에서는 구성 파일에서 참조되는 어셈블리의 부분 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-115">When deploying side by side scenarios where two different versions of a service are deployed, it is necessary to specify partial names of assemblies referenced in configuration files.</span></span> <span data-ttu-id="6c5ce-116">이는 구성 파일이 모든 버전의 서비스에서 공유되며 이러한 서비스가 여러 가지 버전의 .NET Framework에서 실행될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-116">This is because the configuration file is shared across all versions of a service and they could be running under different versions of the .NET Framework.</span></span>  
  
## <a name="systemconfiguration-webconfig-and-appconfig"></a><span data-ttu-id="6c5ce-117">System.Configuration: Web.config 및 App.config</span><span class="sxs-lookup"><span data-stu-id="6c5ce-117">System.Configuration: Web.config and App.config</span></span>  
 <span data-ttu-id="6c5ce-118">WCF의 System.Configuration 구성 시스템을 사용 하 여 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-118">WCF uses the System.Configuration configuration system of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="6c5ce-119">Visual Studio에서 서비스를 구성할 때 Web.config 파일 또는 App.config 파일 중 하나를 사용 하 여 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-119">When configuring a service in Visual Studio, use either a Web.config file or an App.config file to specify the settings.</span></span> <span data-ttu-id="6c5ce-120">구성 파일 이름은 서비스에 대해 선택한 호스팅 환경에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-120">The choice of the configuration file name is determined by the hosting environment you choose for the service.</span></span> <span data-ttu-id="6c5ce-121">IIS를 사용하여 서비스를 호스트하는 경우에는 Web.config 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-121">If you are using IIS to host your service, use a Web.config file.</span></span> <span data-ttu-id="6c5ce-122">다른 호스팅 환경을 사용하는 경우에는 App.config 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-122">If you are using any other hosting environment, use an App.config file.</span></span>  
  
 <span data-ttu-id="6c5ce-123">Visual Studio에서 App.config 라는 파일은 최종 구성 파일을 만드는 데 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-123">In Visual Studio, the file named App.config is used to create the final configuration file.</span></span> <span data-ttu-id="6c5ce-124">구성에 사용되는 최종 이름은 어셈블리 이름에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-124">The final name actually used for the configuration depends on the assembly name.</span></span> <span data-ttu-id="6c5ce-125">예를 들어, "Cohowinery.exe"라는 어셈블리에는 "Cohowinery.exe.config"의 최종 구성 파일 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-125">For example, an assembly named "Cohowinery.exe" has a final configuration file name of "Cohowinery.exe.config".</span></span> <span data-ttu-id="6c5ce-126">그러나 App.config 파일만 수정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-126">However, you only need to modify the App.config file.</span></span> <span data-ttu-id="6c5ce-127">이 파일의 변경 내용은 컴파일 타임에 최종 응용 프로그램 구성 파일에 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-127">Changes made to that file are automatically made to the final application configuration file at compile time.</span></span>  
  
 <span data-ttu-id="6c5ce-128">App.config 파일 사용 시 응용 프로그램이 시작되고 구성이 적용되면 구성 시스템에서는 App.config 파일을 Machine.config 파일의 내용과 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-128">In using an App.config, file the configuration system merges the App.config file with content of the Machine.config file when the application starts and the configuration is applied.</span></span> <span data-ttu-id="6c5ce-129">이 메커니즘을 통해 시스템 수준의 설정이 Machine.config 파일에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-129">This mechanism allows machine-wide settings to be defined in the Machine.config file.</span></span> <span data-ttu-id="6c5ce-130">App.config 파일을 사용하여 Machine.config 파일의 설정을 재정의할 수 있습니다. 또한 Machine.config 파일의 설정이 사용되도록 해당 설정을 잠글 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-130">The App.config file can be used to override the settings of the Machine.config file; you can also lock in the settings in Machine.config file so that they get used.</span></span> <span data-ttu-id="6c5ce-131">Web.config의 경우 구성 시스템에서는 응용 프로그램 디렉터리에 이르는 모든 디렉터리의 Web.config 파일을 적용된 구성에 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-131">In the Web.config case, the configuration system merges the Web.config files in all directories leading up to the application directory into the configuration that gets applied.</span></span> <span data-ttu-id="6c5ce-132">구성과 설정의 우선 순위에 대 한 자세한 내용은 참조 항목에서는 <xref:System.Configuration> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-132">For more information about configuration and the setting priorities, see topics in the <xref:System.Configuration> namespace.</span></span>  
  
## <a name="major-sections-of-the-configuration-file"></a><span data-ttu-id="6c5ce-133">구성 파일의 주요 섹션</span><span class="sxs-lookup"><span data-stu-id="6c5ce-133">Major Sections of the Configuration File</span></span>  
 <span data-ttu-id="6c5ce-134">구성 파일의 주요 섹션에는 다음 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-134">The main sections in the configuration file include the following elements.</span></span>  
  
```xml  
<system.ServiceModel>  
  
   <services>  
   <!—- Define the service endpoints. This section is optional in the new  
    default configuration model in .NET Framework 4. -->  
      <service>  
         <endpoint/>  
      </service>  
   </services>  
  
   <bindings>  
   <!-- Specify one or more of the system-provided binding elements,  
    for example, <basicHttpBinding> -->   
   <!-- Alternatively, <customBinding> elements. -->  
      <binding>  
      <!-- For example, a <BasicHttpBinding> element. -->  
      </binding>  
   </bindings>  
  
   <behaviors>  
   <!-- One or more of the system-provided or custom behavior elements. -->  
      <behavior>  
      <!-- For example, a <throttling> element. -->  
      </behavior>  
   </behaviors>  
  
</system.ServiceModel>  
```  
  
> [!NOTE]
>  <span data-ttu-id="6c5ce-135">바인딩 및 동작 섹션은 선택 사항이며 필요 시에만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-135">The bindings and behaviors sections are optional and are only included if required.</span></span>  
  
### <a name="the-services-element"></a><span data-ttu-id="6c5ce-136">\<서비스 > 요소</span><span class="sxs-lookup"><span data-stu-id="6c5ce-136">The \<services> Element</span></span>  
 <span data-ttu-id="6c5ce-137">`services` 요소에는 응용 프로그램에서 호스트하는 모든 서비스에 대한 사양이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-137">The `services` element contains the specifications for all services the application hosts.</span></span> <span data-ttu-id="6c5ce-138">[!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]의 간소화된 구성 모델부터 이 섹션은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-138">Starting with the simplified configuration model in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], this section is optional.</span></span>  
  
 [<span data-ttu-id="6c5ce-139">\<services></span><span class="sxs-lookup"><span data-stu-id="6c5ce-139">\<services></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/services.md)  
  
### <a name="the-service-element"></a><span data-ttu-id="6c5ce-140">\<서비스 > 요소</span><span class="sxs-lookup"><span data-stu-id="6c5ce-140">The \<service> Element</span></span>  
 <span data-ttu-id="6c5ce-141">각 서비스에는 다음 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-141">Each service has these attributes:</span></span>  
  
-   <span data-ttu-id="6c5ce-142">`name`.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-142">`name`.</span></span> <span data-ttu-id="6c5ce-143">서비스 계약의 구현을 제공하는 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-143">Specifies the type that provides an implementation of a service contract.</span></span> <span data-ttu-id="6c5ce-144">네임스페이스, 마침표, 형식 이름순으로 구성되는 정규화된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-144">This is a fully qualified name which consists of the namespace, a period, and then the type name.</span></span> <span data-ttu-id="6c5ce-145">예를 들면 `"MyNameSpace.myServiceType"`과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-145">For example `"MyNameSpace.myServiceType"`.</span></span>  
  
-   <span data-ttu-id="6c5ce-146">`behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-146">`behaviorConfiguration`.</span></span> <span data-ttu-id="6c5ce-147">`behavior` 요소에 있는 `behaviors` 요소 중 하나의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-147">Specifies the name of one of the `behavior` elements found in the `behaviors` element.</span></span> <span data-ttu-id="6c5ce-148">지정한 동작은 서비스에서 가장을 허용할지 여부와 같은 작업을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-148">The specified behavior governs actions such as whether the service allows impersonation.</span></span> <span data-ttu-id="6c5ce-149">해당 값이 빈 이름이거나 `behaviorConfiguration` 이 제공되지 않으면 기본 서비스 동작 집합이 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-149">If its value is the empty name or no `behaviorConfiguration` is provided then the default set of service behaviors is added to the service.</span></span>  
  
-   [<span data-ttu-id="6c5ce-150">\<service></span><span class="sxs-lookup"><span data-stu-id="6c5ce-150">\<service></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/service.md)  
  
### <a name="the-endpoint-element"></a><span data-ttu-id="6c5ce-151">\<끝점 > 요소</span><span class="sxs-lookup"><span data-stu-id="6c5ce-151">The \<endpoint> Element</span></span>  
 <span data-ttu-id="6c5ce-152">각 끝점에는 다음 특성으로 표시되는 주소, 바인딩 및 계약이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-152">Each endpoint requires an address, a binding, and a contract, which are represented by the following attributes:</span></span>  
  
-   <span data-ttu-id="6c5ce-153">`address`.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-153">`address`.</span></span> <span data-ttu-id="6c5ce-154">절대 주소이거나 서비스의 기본 주소에 대한 상대 주소일 수 있는 서비스의 URI(Uniform Resource Identifier)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-154">Specifies the service's Uniform Resource Identifier (URI), which can be an absolute address or one that is given relative to the base address of the service.</span></span> <span data-ttu-id="6c5ce-155">이 특성이 빈 문자열로 설정되면 서비스에 <xref:System.ServiceModel.ServiceHost> 를 만들 때 지정되는 기본 주소에서 끝점을 사용할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-155">If set to an empty string, it indicates that the endpoint is available at the base address that is specified when creating the <xref:System.ServiceModel.ServiceHost> for the service.</span></span>  
  
-   <span data-ttu-id="6c5ce-156">`binding`.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-156">`binding`.</span></span> <span data-ttu-id="6c5ce-157">일반적으로 <xref:System.ServiceModel.WSHttpBinding>과 같은 시스템 제공 바인딩을 지정하지만 사용자 정의 바인딩을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-157">Typically specifies a system-provided binding like <xref:System.ServiceModel.WSHttpBinding>, but can also specify a user-defined binding.</span></span> <span data-ttu-id="6c5ce-158">지정된 바인딩에 따라 전송 형식, 사용된 보안 및 인코딩 그리고 신뢰할 수 있는 세션, 트랜잭션 또는 스트리밍을 지원하거나 사용할 수 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-158">The binding specified determines the type of transport, security and encoding used, and whether reliable sessions, transactions, or streaming is supported or enabled.</span></span>  
  
-   <span data-ttu-id="6c5ce-159">`bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-159">`bindingConfiguration`.</span></span> <span data-ttu-id="6c5ce-160">바인딩의 기본값을 수정해야 하는 경우 `binding` 요소에서 해당 `bindings` 요소를 구성하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-160">If the default values of a binding must be modified, this can be done by configuring the appropriate `binding` element in the `bindings` element.</span></span> <span data-ttu-id="6c5ce-161">이 특성에는 기본값을 변경하는 데 사용되는 `name` 요소의 `binding` 특성과 동일한 값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-161">This attribute should be given the same value as the `name` attribute of the `binding` element that is used to change the defaults.</span></span> <span data-ttu-id="6c5ce-162">이름을 지정하지 않거나 바인딩에서 `bindingConfiguration` 을 지정하지 않으면 바인딩 형식의 기본 바인딩이 끝점에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-162">If no name is given, or no `bindingConfiguration` is specified in the binding, then the default binding of the binding type is used in the endpoint.</span></span>  
  
-   <span data-ttu-id="6c5ce-163">`contract`.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-163">`contract`.</span></span> <span data-ttu-id="6c5ce-164">계약을 정의하는 인터페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-164">Specifies the interface that defines the contract.</span></span> <span data-ttu-id="6c5ce-165">이 특성은 `name` 요소의 `service` 특성으로 지정된 CLR(공통 언어 런타임)에 구현된 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-165">This is the interface implemented in the common language runtime (CLR) type specified by the `name` attribute of the `service` element.</span></span>  
  
-   [<span data-ttu-id="6c5ce-166">\<끝점 > 요소 참조</span><span class="sxs-lookup"><span data-stu-id="6c5ce-166">\<endpoint> element reference</span></span>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)  
  
### <a name="the-bindings-element"></a><span data-ttu-id="6c5ce-167">\<바인딩 > 요소</span><span class="sxs-lookup"><span data-stu-id="6c5ce-167">The \<bindings> Element</span></span>  
 <span data-ttu-id="6c5ce-168">`bindings` 요소에는 서비스에 정의된 끝점에서 사용할 수 있는 모든 바인딩에 대한 사양이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-168">The `bindings` element contains the specifications for all bindings that can be used by any endpoint defined in any service.</span></span>  
  
 [<span data-ttu-id="6c5ce-169">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6c5ce-169">\<bindings></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-binding-element"></a><span data-ttu-id="6c5ce-170">\<바인딩 > 요소</span><span class="sxs-lookup"><span data-stu-id="6c5ce-170">The \<binding> Element</span></span>  
 <span data-ttu-id="6c5ce-171">`binding` 에 포함 된 요소는 `bindings` 요소는 시스템 제공 바인딩 중 하나가 발생 될 수 있습니다 (참조 [시스템 제공 바인딩](../../../docs/framework/wcf/system-provided-bindings.md)) 또는 사용자 지정 바인딩을 (참조 [사용자 지정 바인딩을](../../../docs/framework/wcf/extending/custom-bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="6c5ce-171">The `binding` elements contained in the `bindings` element can be either one of the system-provided bindings (see [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md)) or a custom binding (see [Custom Bindings](../../../docs/framework/wcf/extending/custom-bindings.md)).</span></span> <span data-ttu-id="6c5ce-172">`binding` 요소에는 `name` 요소의 `bindingConfiguration` 특성에 지정된 끝점과 바인딩을 연관시키는 `endpoint` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-172">The `binding` element has a `name` attribute that correlates the binding with the endpoint specified in the `bindingConfiguration` attribute of the `endpoint` element.</span></span> <span data-ttu-id="6c5ce-173">이름을 지정하지 않는 경우 이 바인딩은 해당 바인딩 형식의 기본값에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-173">If no name is specified then that binding corresponds to the default of that binding type.</span></span>  
  
 <span data-ttu-id="6c5ce-174">서비스와 클라이언트를 구성 하는 방법에 대 한 자세한 내용은 참조 [Windows Communication Foundation 응용 프로그램 구성](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-174">For more information about configuring services and clients, see [Configuring Windows Communication Foundation Applications](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).</span></span>  
  
 [<span data-ttu-id="6c5ce-175">\<binding></span><span class="sxs-lookup"><span data-stu-id="6c5ce-175">\<binding></span></span>](../../../docs/framework/misc/binding.md)  
  
### <a name="the-behaviors-element"></a><span data-ttu-id="6c5ce-176">\<동작 > 요소</span><span class="sxs-lookup"><span data-stu-id="6c5ce-176">The \<behaviors> Element</span></span>  
 <span data-ttu-id="6c5ce-177">서비스의 동작을 정의하는 `behavior` 요소에 대한 컨테이너 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-177">This is a container element for the `behavior` elements that define the behaviors for a service.</span></span>  
  
 [<span data-ttu-id="6c5ce-178">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="6c5ce-178">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
  
### <a name="the-behavior-element"></a><span data-ttu-id="6c5ce-179">\<동작 > 요소</span><span class="sxs-lookup"><span data-stu-id="6c5ce-179">The \<behavior> Element</span></span>  
 <span data-ttu-id="6c5ce-180">각 `behavior` 요소는 `name` 특성으로 식별되며 <`throttling`>과 같은 시스템 제공 동작이나 사용자 지정 동작을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-180">Each `behavior` element is identified by a `name` attribute and provides either a system-provided behavior, such as <`throttling`>, or a custom behavior.</span></span> <span data-ttu-id="6c5ce-181">이름을 지정하지 않는 경우 이 동작 요소는 기본 서비스 또는 끝점 동작에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-181">If no name is given then that behavior element corresponds to the default service or endpoint behavior.</span></span>  
  
 [<span data-ttu-id="6c5ce-182">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="6c5ce-182">\<behavior></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
## <a name="how-to-use-binding-and-behavior-configurations"></a><span data-ttu-id="6c5ce-183">바인딩 및 동작 구성 사용 방법</span><span class="sxs-lookup"><span data-stu-id="6c5ce-183">How to Use Binding and Behavior Configurations</span></span>  
 <span data-ttu-id="6c5ce-184">WCF를 사용 하면 참조 시스템을 사용 하 여 구성에서 끝점 간의 구성을 쉽게 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-184">WCF makes it easy to share configurations between endpoints using a reference system in configuration.</span></span> <span data-ttu-id="6c5ce-185">구성 값을 끝점에 직접 할당하는 대신 바인딩 관련 구성 값은 `bindingConfiguration` 섹션의 `<binding>` 요소로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-185">Rather than directly assigning configuration values to an endpoint, binding-related configuration values are grouped in `bindingConfiguration` elements in the `<binding>` section.</span></span> <span data-ttu-id="6c5ce-186">바인딩 구성은 바인딩에 대한 설정의 명명된 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-186">A binding configuration is a named group of settings on a binding.</span></span> <span data-ttu-id="6c5ce-187">끝점은 이름별로 `bindingConfiguration` 을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-187">Endpoints can then reference the `bindingConfiguration` by name.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
 <system.serviceModel>  
  <bindings>  
    <basicHttpBinding>  
     <binding name="myBindingConfiguration1" closeTimeout="00:01:00" />  
     <binding name="myBindingConfiguration2" closeTimeout="00:02:00" />  
     <binding closeTimeout="00:03:00" />  <!—- Default binding for basicHttpBinding -->  
    </basicHttpBinding>  
     </bindings>  
     <services>  
      <service name="MyNamespace.myServiceType">  
       <endpoint   
          address="myAddress" binding="basicHttpBinding"   
          bindingConfiguration="myBindingConfiguration1"  
          contract="MyContract"  />  
       <endpoint   
          address="myAddress2" binding="basicHttpBinding"   
          bindingConfiguration="myBindingConfiguration2"  
          contract="MyContract" />  
       <endpoint   
          address="myAddress3" binding="basicHttpBinding"   
          contract="MyContract" />  
       </service>  
      </services>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="6c5ce-188">`name` 의 `bindingConfiguration` 은 `<binding>` 요소에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-188">The `name` of the `bindingConfiguration` is set in the `<binding>` element.</span></span> <span data-ttu-id="6c5ce-189">`name` 바인딩 형식 범위 내에서 고유한 문자열 이어야 합니다-이 경우에 [< basicHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), 이거나 기본 바인딩을 참조 하는 빈 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-189">The `name` must be a unique string within the scope of the binding type—in this case the [<basicHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), or an empty value to refer to the default binding.</span></span> <span data-ttu-id="6c5ce-190">끝점은 `bindingConfiguration` 특성을 이 문자열에 설정하여 구성에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-190">The endpoint links to the configuration by setting the `bindingConfiguration` attribute to this string.</span></span>  
  
 <span data-ttu-id="6c5ce-191">`behaviorConfiguration` 은 다음 샘플과 동일한 방식으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-191">A `behaviorConfiguration` is implemented the same way, as illustrated in the following sample.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myBehavior">  
           <callbackDebug includeExceptionDetailInFaults="true" />  
         </behavior>  
      </endpointBehaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
  
    </behaviors>  
    <services>  
     <service name="NewServiceType">  
       <endpoint   
          address="myAddress3" behaviorConfiguration="myBehavior"  
          binding="basicHttpBinding"  
          contract="MyContract" />  
      </service>  
    </services>  
   </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="6c5ce-192">기본 서비스 동작 집합이 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-192">Note that the default set of service behaviors are added to the service.</span></span> <span data-ttu-id="6c5ce-193">이 시스템에서는 설정을 다시 정의하지 않고 끝점이 일반 구성을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-193">This system allows endpoints to share common configurations without redefining the settings.</span></span> <span data-ttu-id="6c5ce-194">시스템 수준의 범위가 필요하면 Machine.config에서 동작 구성 또는 바인딩을 만듭니다. 모든 App.config 파일에서 구성 설정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-194">If machine-wide scope is required, create the binding or behavior configuration in Machine.config. The configuration settings are available in all App.config files.</span></span> <span data-ttu-id="6c5ce-195">[Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) 를 사용하면 구성을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-195">The [Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) makes it easy to create configurations.</span></span>  
  
## <a name="behavior-merge"></a><span data-ttu-id="6c5ce-196">동작 병합</span><span class="sxs-lookup"><span data-stu-id="6c5ce-196">Behavior Merge</span></span>  
 <span data-ttu-id="6c5ce-197">일반적인 동작의 집합을 지속적으로 사용하려는 경우 이 동작 병합 기능을 통해 동작을 더욱 쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-197">The behavior merge feature makes it easier to manage behaviors when you want a set of common behaviors to be used consistently.</span></span> <span data-ttu-id="6c5ce-198">이 기능을 사용하면 여러 가지 수준의 구성 계층에서 동작을 지정하고 서비스가 여러 가지 수준의 구성 계층에서 동작을 상속하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-198">This feature allows you to specify behaviors at different levels of the configuration hierarchy and have services inherit behaviors from multiple levels of the configuration hierarchy.</span></span> <span data-ttu-id="6c5ce-199">이에 대한 동작 방식을 보여 주기 위해 IIS에서 다음과 같은 가상 디렉터리 레이아웃이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-199">To illustrate how this works assume you have the following virtual directory layout in IIS:</span></span>  
  
 <span data-ttu-id="6c5ce-200">~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc</span><span class="sxs-lookup"><span data-stu-id="6c5ce-200">~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc</span></span>  
  
 <span data-ttu-id="6c5ce-201">또한 ~\Web.config 파일의 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-201">And your ~\Web.config file has the following contents:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="6c5ce-202">또한 ~\Child\Web.config에 있는 자식 Web.config의 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-202">And you have a child Web.config located at ~\Child\Web.config with the following contents:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="6c5ce-203">~\Child\Service.svc에 있는 서비스는 serviceDebug 및 serviceMetadata 동작이 둘 다 있는 것처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-203">The service located at ~\Child\Service.svc will behave as though it has both the serviceDebug and serviceMetadata behaviors.</span></span> <span data-ttu-id="6c5ce-204">~\Service.svc에 있는 서비스에는 serviceDebug 동작만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-204">The service located at ~\Service.svc will only have the serviceDebug behavior.</span></span> <span data-ttu-id="6c5ce-205">결과적으로 동일한 이름(이 경우 빈 문자열)의 두 동작 컬렉션이 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-205">What happens is that the two behavior collections with the same name (in this case the empty string) are merged.</span></span>  
  
 <span data-ttu-id="6c5ce-206">사용 하 여 동작 컬렉션을 지울 수도 있습니다는 \<지우기 > 태그를 사용 하 여 컬렉션에서 개별 동작을 제거할는 \<제거 > 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-206">You can also clear behavior collections by using the \<clear> tag and removed individual behaviors from the collection by using the \<remove> tag.</span></span> <span data-ttu-id="6c5ce-207">예를 들어 다음 두 구성을 사용하면 자식 서비스에 serviceMetadata 동작만 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-207">For example, the following two configuration results in the child service having only the serviceMetadata behavior:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <remove name="serviceDebug"/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <clear/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="6c5ce-208">동작 병합은 위에 나와 있는 것처럼 이름 없는 동작 컬렉션뿐만 아니라 명명된 동작 컬렉션에도 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-208">Behavior merge is done for nameless behavior collections as shown above and named behavior collections as well.</span></span>  
  
 <span data-ttu-id="6c5ce-209">동작 병합은 IIS 호스팅 환경에서 수행되며 이 환경에서 Web.config 파일은 루트 Web.config 파일 및 machine.config와 계층적으로 병합됩니다. 그러나 응용 프로그램 환경에서도 동작 병합이 수행되며 이 환경에서는 machine.config가 App.config 파일과 병합될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-209">Behavior merge works in the IIS hosting environment, in which Web.config files merge hierarchically with the root Web.config file and machine.config. But it also works in the application environment, where machine.config can merge with the App.config file.</span></span>  
  
 <span data-ttu-id="6c5ce-210">동작 병합은 구성의 끝점 동작과 서비스 동작에 모두 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-210">Behavior merge applies to both endpoint behaviors and service behaviors in configuration.</span></span>  
  
 <span data-ttu-id="6c5ce-211">자식 동작 컬렉션에 부모 동작 컬렉션에 이미 있는 동작이 포함되어 있으면 자식 동작이 부모 동작을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-211">If a child behavior collection contains a behavior that’s already present in the parent behavior collection, the child behavior overrides the parent.</span></span> <span data-ttu-id="6c5ce-212">따라서 부모 동작 컬렉션에 `<serviceMetadata httpGetEnabled="False" />` 있고 자식 동작 컬렉션에 `<serviceMetadata httpGetEnabled="True" />`자식 동작은 동작 컬렉션의 부모 동작을 재정의 하 고 httpGetEnabled는 "true"입니다.</span><span class="sxs-lookup"><span data-stu-id="6c5ce-212">So if a parent behavior collection had `<serviceMetadata httpGetEnabled="False" />` and a child behavior collection had `<serviceMetadata httpGetEnabled="True" />`, the child behavior would override the parent behavior in the behavior collection and httpGetEnabled would be "true".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c5ce-213">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c5ce-213">See Also</span></span>  
 [<span data-ttu-id="6c5ce-214">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="6c5ce-214">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="6c5ce-215">Windows Communication Foundation 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="6c5ce-215">Configuring Windows Communication Foundation Applications</span></span>](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 [<span data-ttu-id="6c5ce-216">\<service></span><span class="sxs-lookup"><span data-stu-id="6c5ce-216">\<service></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/service.md)  
 [<span data-ttu-id="6c5ce-217">\<binding></span><span class="sxs-lookup"><span data-stu-id="6c5ce-217">\<binding></span></span>](../../../docs/framework/misc/binding.md)
