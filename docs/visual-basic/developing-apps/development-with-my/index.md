---
title: My를 사용한 개발(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWpfExtension.Windows
helpviewer_keywords:
- My object
- My namespace
- My feature
- Visual Basic, programming in
ms.assetid: f1d04509-5e46-4551-9f9f-94334a121fca
ms.openlocfilehash: f13e7348eb1c63e8256a48da7a8f5a8e357c72ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584426"
---
# <a name="development-with-my-visual-basic"></a><span data-ttu-id="eeead-102">My를 사용한 개발(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eeead-102">Development with My (Visual Basic)</span></span>
<span data-ttu-id="eeead-103">Visual Basic은 강력한 기능을 지원하며 생산성 및 사용 편의성을 향상시키는 응용 프로그램을 신속하게 개발할 수 있는 새로운 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eeead-103">Visual Basic provides new features for rapid application development that improve productivity and ease of use while delivering power.</span></span> <span data-ttu-id="eeead-104">이러한 기능 중 하나인 `My`는 응용 프로그램 및 해당 런타임 환경과 관련된 정보와 기본 개체 인스턴스에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eeead-104">One of these features, called `My`, provides access to information and default object instances that are related to the application and its run-time environment.</span></span> <span data-ttu-id="eeead-105">이 정보는 IntelliSense를 통해 검색할 수 있는 형식으로 구성되고 용도에 따라 논리적으로 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeead-105">This information is organized in a format that is discoverable through IntelliSense and logically delineated according to use.</span></span>  
  
 <span data-ttu-id="eeead-106">`My`의 최상위 멤버는 개체로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="eeead-106">Top-level members of `My` are exposed as objects.</span></span> <span data-ttu-id="eeead-107">각 개체는 `Shared` 멤버가 있는 네임스페이스 또는 클래스와 비슷하게 동작하며 관련 멤버의 집합을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="eeead-107">Each object behaves similarly to a namespace or a class with `Shared` members, and it exposes a set of related members.</span></span>  
  
 <span data-ttu-id="eeead-108">다음 표에서는 최상위 `My` 개체와 서로 간의 관계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eeead-108">This table shows the top-level `My` objects and their relationship to each other.</span></span>  
  
 <span data-ttu-id="eeead-109">![My에 대한 개체 모델](../../../visual-basic/developing-apps/development-with-my/media/myobjmodel.gif "MyObjModel")</span><span class="sxs-lookup"><span data-stu-id="eeead-109">![Object Model for My](../../../visual-basic/developing-apps/development-with-my/media/myobjmodel.gif "MyObjModel")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eeead-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="eeead-110">In This Section</span></span>  
 [<span data-ttu-id="eeead-111">My.Application, My.Computer 및 My.User를 사용한 작업 수행</span><span class="sxs-lookup"><span data-stu-id="eeead-111">Performing Tasks with My.Application, My.Computer, and My.User</span></span>](../../../visual-basic/developing-apps/development-with-my/performing-tasks-with-my-application-my-computer-and-my-user.md)  
 <span data-ttu-id="eeead-112">정보 및 기능에 액세스할 수 있도록 하는 세 개의 핵심 `My` 개체 `My.Application`, `My.Computer` 및 `My.User`에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eeead-112">Describes the three central `My` objects, `My.Application`, `My.Computer`, and `My.User`, which provide access to information and functionality</span></span>  
  
 [<span data-ttu-id="eeead-113">My.Forms 및 My.WebServices에서 제공하는 기본 개체 인스턴스</span><span class="sxs-lookup"><span data-stu-id="eeead-113">Default Object Instances Provided by My.Forms and My.WebServices</span></span>](../../../visual-basic/developing-apps/development-with-my/default-object-instances-provided-by-my-forms-and-my-webservices.md)  
 <span data-ttu-id="eeead-114">응용 프로그램에서 사용되는 폼, 데이터 소스 및 XML Web services에 액세스할 수 있도록 하는 `My.Forms` 및 `My.WebServices` 개체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eeead-114">Describes the `My.Forms` and `My.WebServices` objects, which provide access to forms, data sources, and XML Web services used by your application.</span></span>  
  
 [<span data-ttu-id="eeead-115">My.Resources 및 My.Settings를 사용한 신속한 응용 프로그램 개발</span><span class="sxs-lookup"><span data-stu-id="eeead-115">Rapid Application Development with My.Resources and My.Settings</span></span>](../../../visual-basic/developing-apps/development-with-my/rapid-application-development-with-my-resources-and-my-settings.md)  
 <span data-ttu-id="eeead-116">응용 프로그램의 리소스 및 설정에 액세스할 수 있도록 하는 `My.Resources` 및 `My.Settings` 개체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eeead-116">Describes the `My.Resources` and `My.Settings` objects, which provide access to an application's resources and settings.</span></span>  
  
 [<span data-ttu-id="eeead-117">Visual Basic 응용 프로그램 모델 개요</span><span class="sxs-lookup"><span data-stu-id="eeead-117">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="eeead-118">Visual Basic 응용 프로그램 시작/종료 모델에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeead-118">Describes the Visual Basic Application Startup/Shutdown model.</span></span>  
  
 [<span data-ttu-id="eeead-119">My가 프로젝트 형식에 의존하는 방식</span><span class="sxs-lookup"><span data-stu-id="eeead-119">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="eeead-120">여러 다른 프로젝트 형식에서 사용할 수 있는 `My` 기능에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eeead-120">Gives details on which `My` features are available in different project types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeead-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eeead-121">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [<span data-ttu-id="eeead-122">My.Forms 개체</span><span class="sxs-lookup"><span data-stu-id="eeead-122">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [<span data-ttu-id="eeead-123">My.WebServices 개체</span><span class="sxs-lookup"><span data-stu-id="eeead-123">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [<span data-ttu-id="eeead-124">My가 프로젝트 형식에 의존하는 방식</span><span class="sxs-lookup"><span data-stu-id="eeead-124">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
