---
title: "Windows 서비스 응용 프로그램 개발"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: "18"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 2912568e967c8c6096842b1b4f24eac88318dffb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="developing-windows-service-applications"></a><span data-ttu-id="a5782-102">Windows 서비스 응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="a5782-102">Developing Windows Service Applications</span></span>
<span data-ttu-id="a5782-103">Microsoft를 사용 하 여 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 또는 Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK를 쉽게 만들 수 있습니다 서비스 서비스로 설치 하는 응용 프로그램을 만들어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5782-103">Using Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or the Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="a5782-104">이 유형의 응용 프로그램에는 Windows 서비스를 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5782-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="a5782-105">Framework 기능을 사용 있습니다 수는 서비스를 만들, 설치, 시작, 중지 및 그렇지 않은 경우의 동작을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5782-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="a5782-106">C + +에 대 한 Windows 서비스 템플릿은 Visual Studio 2010에 포함 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="a5782-106">The Windows service template for C++ was not included in Visual Studio 2010.</span></span> <span data-ttu-id="a5782-107">Windows 서비스를 만들려면 Visual C# 또는 Visual Basic, 필요한 경우 기존 c + + 코드 상호 작용할 수에서 관리 코드에서 서비스를 만들 수 있습니다 또는 네이티브 c + +에서를 사용 하 여 Windows 서비스를 만들 수는 [ATL프로젝트마법사](/cpp/atl/reference/atl-project-wizard).</span><span class="sxs-lookup"><span data-stu-id="a5782-107">To create a Windows service, you can either create a service in managed code in Visual C# or Visual Basic, which could interoperate with existing C++ code if required, or you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a5782-108">단원 내용</span><span class="sxs-lookup"><span data-stu-id="a5782-108">In This Section</span></span>  
 [<span data-ttu-id="a5782-109">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="a5782-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 <span data-ttu-id="a5782-110">서비스 및 서비스 응용 프로그램 다른 공통 프로젝트 형식에서 어떻게 다른 지의 수명을 Windows 서비스 응용 프로그램에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5782-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>  
  
 [<span data-ttu-id="a5782-111">연습: 구성 요소 디자이너에는 Windows 서비스 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="a5782-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 <span data-ttu-id="a5782-112">서비스를 만드는 예제를 제공 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 및 Visual C#입니다.</span><span class="sxs-lookup"><span data-stu-id="a5782-112">Provides an example of creating a service in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] and Visual C#.</span></span>  
  
 [<span data-ttu-id="a5782-113">서비스 응용 프로그램 프로그래밍 아키텍처</span><span class="sxs-lookup"><span data-stu-id="a5782-113">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 <span data-ttu-id="a5782-114">서비스 프로그래밍에 사용 되는 언어 요소에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5782-114">Explains the language elements used in service programming.</span></span>  
  
 [<span data-ttu-id="a5782-115">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="a5782-115">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 <span data-ttu-id="a5782-116">만들기 및 Windows 서비스 프로젝트 템플릿을 사용 하 여 Windows 서비스를 구성 하는 과정을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5782-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a5782-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="a5782-117">Related Sections</span></span>  
 <xref:System.ServiceProcess.ServiceBase>  
 <span data-ttu-id="a5782-118">주요 기능에 설명 된 <xref:System.ServiceProcess.ServiceBase> 서비스를 만드는 데 사용 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a5782-118">Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 <span data-ttu-id="a5782-119">기능을 설명는 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스와 함께 사용 하는 <xref:System.ServiceProcess.ServiceInstaller> 클래스 설치 하 고 서비스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5782-119">Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 <span data-ttu-id="a5782-120">기능을 설명는 <xref:System.ServiceProcess.ServiceInstaller> 클래스와 함께 사용 하는 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스 설치 하 고 서비스를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5782-120">Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>  
  
 [<span data-ttu-id="a5782-121">NIB 템플릿에서 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a5782-121">NIB Creating Projects from Templates</span></span>](http://msdn.microsoft.com/en-us/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 <span data-ttu-id="a5782-122">프로젝트 선택 하는 방법과이 장의에 사용 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a5782-122">Describes the projects types used in this chapter and how to choose between them.</span></span>
