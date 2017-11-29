---
title: '@ServiceHost'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed64a90131fcd8f2d9f2120c03db4a21d8dc6efe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="servicehost"></a>@ServiceHost
<span data-ttu-id="cecc1-101">서비스 호스트를 생성하는 데 사용되는 팩토리를 호스트할 서비스 및 .svc 파일에 제공된 호스팅 코드에 액세스하거나 이를 컴파일하는 데 필요한 다른 프로그래밍 요소에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-101">Associates the factory used to produce the service host with the service to be hosted and other programming aspects required to access or compile the hosting code provided in the .svc file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cecc1-102">구문</span><span class="sxs-lookup"><span data-stu-id="cecc1-102">Syntax</span></span>  
  
```  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## <a name="attributes"></a><span data-ttu-id="cecc1-103">특성</span><span class="sxs-lookup"><span data-stu-id="cecc1-103">Attributes</span></span>  
  
#### <a name="service"></a><span data-ttu-id="cecc1-104">서비스</span><span class="sxs-lookup"><span data-stu-id="cecc1-104">Service</span></span>  
 <span data-ttu-id="cecc1-105">호스트되는 서비스의 CLR 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-105">The CLR type name of the service hosted.</span></span> <span data-ttu-id="cecc1-106">이 이름은 하나 이상의 서비스 계약을 구현하는 형식의 정규화된 이름이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-106">This should be a qualified name of a type that implements one or more of the service contacts.</span></span>  
  
#### <a name="factory"></a><span data-ttu-id="cecc1-107">Factory</span><span class="sxs-lookup"><span data-stu-id="cecc1-107">Factory</span></span>  
 <span data-ttu-id="cecc1-108">서비스 호스트를 인스턴스화하는 데 사용되는 서비스 호스트 팩터리의 CLR 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-108">The CLR type name of the service host factory used to instantiate the service host.</span></span> <span data-ttu-id="cecc1-109">이 특성은 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-109">This attribute is optional.</span></span> <span data-ttu-id="cecc1-110">지정되지 않은 경우 <xref:System.ServiceModel.Activation.ServiceHostFactory>의 인스턴스를 반환하는 <xref:System.ServiceModel.ServiceHost> 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-110">If unspecified, the default <xref:System.ServiceModel.Activation.ServiceHostFactory> is used, which returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
#### <a name="debug"></a><span data-ttu-id="cecc1-111">디버그</span><span class="sxs-lookup"><span data-stu-id="cecc1-111">Debug</span></span>  
 <span data-ttu-id="cecc1-112">디버그 기호를 사용하여 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스를 컴파일해야 할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-112">Indicates whether the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] service should be compiled with debug symbols.</span></span> <span data-ttu-id="cecc1-113">디버그 기호를 사용하여 `true` 서비스를 컴파일해야 하면 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-113">`true` if the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service should be compiled with debug symbols; otherwise, `false`.</span></span>  
  
#### <a name="language"></a><span data-ttu-id="cecc1-114">언어</span><span class="sxs-lookup"><span data-stu-id="cecc1-114">Language</span></span>  
 <span data-ttu-id="cecc1-115">파일(.svc) 내의 인라인 코드를 모두 컴파일할 때 사용되는 언어를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-115">Specifies the language used when compiling all the inline code within file (.svc).</span></span> <span data-ttu-id="cecc1-116">C#, Visual Basic .NET 및 JScript .NET을 각각 나타내는 C#, VB 및 JS를 비롯한 모든 .NET 지원 언어를 값으로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-116">The values can represent any .NET-supported language, including C#, VB, and JS, which refer to C#, Visual Basic .NET, and JScript .NET, respectively.</span></span> <span data-ttu-id="cecc1-117">이 특성은 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-117">This attribute is optional.</span></span>  
  
#### <a name="codebehind"></a><span data-ttu-id="cecc1-118">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="cecc1-118">CodeBehind</span></span>  
 <span data-ttu-id="cecc1-119">XML Web services를 구현하는 클래스가 동일한 파일에 있지 않고, 어셈블리로 컴파일되어 있지 않으며, \Bin 디렉터리에 저장된 경우 XML Web services를 구현하는 소스 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-119">Specifies the source file that implements the XML Web service, when the class that implements the XML Web service does not reside in the same file and has not been compiled into an assembly and placed in the \Bin directory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cecc1-120">설명</span><span class="sxs-lookup"><span data-stu-id="cecc1-120">Remarks</span></span>  
 <span data-ttu-id="cecc1-121">서비스를 호스트하는 데 사용되는 <xref:System.ServiceModel.ServiceHost>는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 프로그래밍 모델 내의 확장 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-121">The <xref:System.ServiceModel.ServiceHost> used to host the service is a point of extensibility within the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] programming model.</span></span> <span data-ttu-id="cecc1-122">팩터리 패턴은 호스팅 환경에서 직접 인스턴스화하면 안 되는 다형 형식이므로 <xref:System.ServiceModel.ServiceHost>를 인스턴스화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-122">A factory pattern is used to instantiate the <xref:System.ServiceModel.ServiceHost> because it is, potentially, a polymorphic type that the hosting environment should not instantiate directly.</span></span>  
  
 <span data-ttu-id="cecc1-123">기본 구현에서는 <xref:System.ServiceModel.Activation.ServiceHostFactory>를 사용하여 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-123">The default implementation uses <xref:System.ServiceModel.Activation.ServiceHostFactory> to create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="cecc1-124">에 팩터리 구현의 CLR 형식 이름을 지정 하 여 팩터리를 직접 (파생된 호스트를 반환 하나)를 제공할 수 있습니다 하지만 [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-124">But you can provide your own factory (one that returns your derived host) by specifying the CLR type name of your factory implementation in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive.</span></span>  
  
 <span data-ttu-id="cecc1-125">를 사용 하려면 사용자 고유의 사용자 지정 서비스 호스트 팩터리 기본 팩터리 대신 제공에 형식 이름을 [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 다음과 같이 지시문:</span><span class="sxs-lookup"><span data-stu-id="cecc1-125">To use you own custom service host factory instead of the default factory, just provide the type name in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive as follows:</span></span>  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 <span data-ttu-id="cecc1-126">팩터리 구현을 가능하면 간단하게 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-126">Keep the factory implementations as light as possible.</span></span> <span data-ttu-id="cecc1-127">사용자 지정 논리가 많은 경우 팩터리 내부 대신 호스트 내부에 해당 로직을 배치하면 코드를 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-127">If you have lots of custom logic, your code is more reusable if you put that logic inside your host instead of inside the factory.</span></span>  
  
 <span data-ttu-id="cecc1-128">예를 들어, AJAX 사용 끝점을 사용할 수 있도록 `MyService`, 지정는 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 의 값에 대 한는 `Factory` 특성 기본값 대신 <xref:System.ServiceModel.Activation.ServiceHostFactory>에 [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 으로 지시문 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cecc1-128">For example, to enable an AJAX-enabled endpoint for `MyService`, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> for the value of the `Factory` attribute, instead of the default <xref:System.ServiceModel.Activation.ServiceHostFactory>, in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cecc1-129">예제</span><span class="sxs-lookup"><span data-stu-id="cecc1-129">Example</span></span>  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cecc1-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cecc1-130">See Also</span></span>  
 [<span data-ttu-id="cecc1-131">사용자 지정 서비스 호스트</span><span class="sxs-lookup"><span data-stu-id="cecc1-131">Custom Service Host</span></span>](../../../../../docs/framework/wcf/samples/custom-service-host.md)
