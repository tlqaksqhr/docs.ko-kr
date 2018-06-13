---
title: Windows 서비스 응용 프로그램 개발
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
manager: douge
ms.openlocfilehash: af6e4bf7697b3139f6809295737fdd0d90b7f013
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512270"
---
# <a name="developing-windows-service-applications"></a><span data-ttu-id="f1f61-102">Windows 서비스 응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="f1f61-102">Developing Windows Service Applications</span></span>
<span data-ttu-id="f1f61-103">Microsoft Visual Studio나 Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK를 사용하면 서비스로 설치되는 응용 프로그램을 만들어 서비스를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-103">Using Microsoft Visual Studio or the Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="f1f61-104">이 유형의 응용 프로그램을 Windows 서비스라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="f1f61-105">프레임워크 기능을 사용하여 서비스를 만들고 설치하고 시작 및 중지할 수 있으며 서비스 동작을 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f1f61-106">C++용 Windows 서비스 템플릿은 Visual Studio 2010에 포함되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-106">The Windows service template for C++ was not included in Visual Studio 2010.</span></span> <span data-ttu-id="f1f61-107">Windows 서비스를 만들려면 Visual C#이나 Visual Basic에서 관리 코드로 서비스를 만들거나(필요한 경우 이러한 코드와 기존 C++ 코드를 함께 사용할 수 있음) 네이티브 C++에서 [ATL 프로젝트 마법사](/cpp/atl/reference/atl-project-wizard)를 사용하여 Windows 서비스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-107">To create a Windows service, you can either create a service in managed code in Visual C# or Visual Basic, which could interoperate with existing C++ code if required, or you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1f61-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="f1f61-108">In This Section</span></span>  
 [<span data-ttu-id="f1f61-109">Windows 서비스 응용 프로그램 소개</span><span class="sxs-lookup"><span data-stu-id="f1f61-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 <span data-ttu-id="f1f61-110">Windows 서비스 응용 프로그램, 서비스 수명 및 서비스 응용 프로그램이 다른 일반적인 프로젝트 유형과 다른 점에 대해 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>  
  
 [<span data-ttu-id="f1f61-111">연습: 구성 요소 디자이너에서 Windows 서비스 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="f1f61-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 <span data-ttu-id="f1f61-112">Visual Basic 및 Visual C#에서 서비스를 만드는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-112">Provides an example of creating a service in Visual Basic and Visual C#.</span></span>  
  
 [<span data-ttu-id="f1f61-113">서비스 응용 프로그램 프로그래밍 아키텍처</span><span class="sxs-lookup"><span data-stu-id="f1f61-113">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 <span data-ttu-id="f1f61-114">서비스 프로그래밍에서 사용되는 언어 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-114">Explains the language elements used in service programming.</span></span>  
  
 [<span data-ttu-id="f1f61-115">방법: Windows 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="f1f61-115">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 <span data-ttu-id="f1f61-116">Windows 서비스 프로젝트 템플릿을 사용하여 Windows 서비스를 만들고 구성하는 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f1f61-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f1f61-117">Related Sections</span></span>  
 <xref:System.ServiceProcess.ServiceBase>  
 <span data-ttu-id="f1f61-118">서비스를 만드는 데 사용되는 <xref:System.ServiceProcess.ServiceBase> 클래스의 주요 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-118">Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 <span data-ttu-id="f1f61-119">서비스를 설치 및 제거하기 위해 <xref:System.ServiceProcess.ServiceInstaller> 클래스와 함께 사용되는 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-119">Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 <span data-ttu-id="f1f61-120">서비스를 설치 및 제거하기 위해 <xref:System.ServiceProcess.ServiceProcessInstaller> 클래스와 함께 사용되는 <xref:System.ServiceProcess.ServiceInstaller> 클래스의 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-120">Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>  
  
 <span data-ttu-id="f1f61-121">[NIB Creating Projects from Templates](http://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)(NIB 템플릿에서 프로젝트 만들기)</span><span class="sxs-lookup"><span data-stu-id="f1f61-121">[NIB Creating Projects from Templates](http://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)</span></span>  
 <span data-ttu-id="f1f61-122">이 장에서 사용되는 프로젝트 유형과 이들 유형 중에서 선택하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1f61-122">Describes the projects types used in this chapter and how to choose between them.</span></span>
